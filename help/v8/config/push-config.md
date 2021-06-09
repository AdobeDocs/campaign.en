---
product: Adobe Campaign
title: Integrate Campaign SDKs with your app
description: Learn how to integrate Campaign Android and iOS SDKs with your app
version: v8
feature: Push
role: Developer
level: Experienced
hide: yes
hidefromtoc: yes
---
# Integrate Campaign SDKs with your app {#integrate-campaign-sdk}

Use Campaign SDKs for iOS and Android to facilitate the integration of your mobile application into the Adobe Campaign platform.

Android and iOS supported versions, and Cammpaign SDKs compatible versions for Campaign v8 are listed in the [Compatibility matrix](../../rn/using/compatibility-matrix.md#MobileSDK) .

>[!NOTE]
>
>As a Campaign administrator, you can download Campaign SDKs from the [Experience Cloud Software Distribution](https://experience.adobe.com/#/downloads/content/software-distributicampaign.html). For more information, contact [Adobe Customer Care](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).


## Declare integration settings {#declaring-integration-settings}

To integrate Campaign SDK into the mobile application, the functional administrator must provide the following information to the developer:

* **An integration key**: to enable the Adobe Campaign platform to identify the mobile application.

  >[!NOTE]
  >
  >This integration key is entered in the Adobe Campaign console, in the **[!UICONTROL Information]** tab of service dedicated to the mobile application. Refer to [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app).

* **A tracking URL**: that matches the address of the Adobe Campaign tracking server.
* **A marketing URL**: to enable the collection of subscriptions.

* **In Android**:

  ```
  Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
  Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
  Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
  ```

* **In iOS**:

  ```
  Neolane_SDK *nl = [Neolane_SDK getInstance];
  [nl setMarketingHost:strMktHost];
  [nl setTrackingHost:strTckHost];
  [nl setIntegrationKey:strIntegrationKey];
  ```

## Integrate Android SDK

Android SDK is a jar library written in JAVA. It allows Android developers to integrate with Adobe Campaign: register a new device, link the device with a user, track behaviour, and more.

In this section, learn how to use the Android SDK in an Android application implementing [Google Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging/).

### Configure FCM

To use the push notification on Android, you must have a FCM account, configure your Android application to receive your notification and link your application to the FCM account. Learn more in [Google Documentation](https://firebase.google.com/docs/cloud-messaging/).

Refer to [Google Documentation](https://firebase.google.com/docs/android/setup) to add Firebase to your Android project.

Learn how to implement FCM in your application in [Google Documentation](https://firebase.google.com/docs/android/setup).

>[!NOTE]
>
> * Do not forget to download and add the google-services.json to your project.
>
> * The `apiKey` must match with the `projectKey` set in the Adobe Campaign Mobile Application linked to this Android application.

### Configure Android SDK

1. **Initialize the SDK**

    Before using the Android SDK, you need to initialize it. The SDK initialization can be done in the `onCreate` function of an activity.

    ```
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
    
        // initialize Neolane sdk
        SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
    
        Neolane.getInstance().setIntegrationKey(settings.getString(YourApplicationActivity.APPUUID_NAME, YourApplicationActivity.DFT_APPUUID));
        Neolane.getInstance().setMarketingHost(settings.getString(YourApplicationActivity.SOAPRT_NAME, YourApplicationActivity.DFT_SOAPRT));
        Neolane.getInstance().setTrackingHost(settings.getString(YourApplicationActivity.TRACKRT_NAME, YourApplicationActivity.DFT_TRACKRT));
        ...
    }
    ```

    The `IntegrationKey` must match with the 'IntegrationKey' set in the Adobe Campaign Mobile Application linked to this Android application.

2. **Register the mobile device to Adobe Campaign server**

    The registration function enables you to:

    * send the notification ID or push ID (deviceToken for iOS and registrationID for Android) to Adobe Campaign.
    * recover the reconciliation key or userKey (email or account number, for instance)

    You must register you device to Adobe Campaign, at the app initialization or on user action. It can be easily done using the `registerDevice` method.

    ```
    public void onClick(View v)
    {
    SharedPreferences settings = this.context.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
    EditText mailEdit = (EditText) this.context.findViewById(R.id.editText1);
    
    final String FCMRegistrationId = FirebaseInstanceId.getInstance().getToken();
    if (FCMRegistrationId != null)
        NeoTripActivity.registerOnNeolane(this.context, FCMRegistrationId, mailEdit.getText().toString());
    
    }
    ```
    
    YourApplicationActivity.java

    ```
    public static void registerOnNeolane(final Context ctx, String registrationId, String userKey)
    {
        NeolaneAsyncRunner neolaneAs = new NeolaneAsyncRunner(Neolane.getInstance());
        // Additional Subscription Parameters
        Map<String,Object> additionnalParam = new HashMap<String, Object>();
        additionnalParam.clear();
        SharedPreferences settings = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
        if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN1_NAME, false))
        {
            additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME1_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE1_NAME, ""));   
        }
        if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN2_NAME, false))
        {
            additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME2_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE2_NAME, ""));   
        }
        if ( additionnalParam.isEmpty() )
        {
            additionnalParam = null;
        }
        // Neolane Registration
        neolaneAs.registerDevice(registrationId, userKey, additionnalParam, ctx, new RequestListener() {
        public void onComplete(String e, Object obj)
        {
            Intent upd = new Intent();
            upd.setAction(BROADCAST_NEWREGISTER_ACTION);
            ctx.sendBroadcast(upd);
        }
    
        public void onNeolaneException(NeolaneException e, Object obj)
        {
            sendErrorMsg(e.getErrorString());
        }
    
        public void onIOException(IOException e, Object obj)
        {
            sendErrorMsg(e.getMessage());
        }
    
        public void sendErrorMsg(String err)
        {
            SharedPreferences.Editor edit = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE).edit();
            edit.putBoolean(YourApplicationActivity.REGISTRATION_ERROR_NEOLANE_KEYNAME, true);
            edit.commit();
            Intent toast = new Intent();
            toast.setAction(BROADCAST_TOAST_DISPLAY_TEXT);
            toast.putExtra("text", "An error happened, please register again (" + err + ")");
            ctx.sendBroadcast(toast);
        }
        });
    }
    ```

1. **Notify Campaign when the user's mobile device token changes**

    We advise you use the `registerDevice` function when calling the `onTokenRefresh` function to notify Adobe Campaign of the change in the user's mobile device token.

    For example:

    YourApplicationFirebaseInstanceIDService.java

    ```
    package com.android.YourApplication;
    
    import android.content.Context;
    import android.content.SharedPreferences;
    import android.util.Log;
    
    import com.google.firebase.iid.FirebaseInstanceId;
    import com.google.firebase.iid.FirebaseInstanceIdService;
    
    import static android.content.SharedPreferences.*;
    
    public class YourApplicationFirebaseInstanceIDService extends FirebaseInstanceIdService 
    {
        @Override
        public void onTokenRefresh() 
        {
        SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
        if (!settings.getBoolean(YourApplicationActivity.USE_GCM, false))
            {
            String refreshedToken = FirebaseInstanceId.getInstance().getToken();
            String userKey = settings.getString(YourApplicationActivity.USERKEY_NAME, "");
            Editor edit = settings.edit();
            edit.putString(YourApplicationActivity.FCM_REGISTRATIONID_NAME, refreshedToken);
            edit.commit();
            YourApplicationActivity.registerOnNeolane(this, refreshedToken, userKey);
            }
        }
    }
    ```
    
1. **Configure Firebase Messaging Service**

    Extend the `FirebaseMessagingService` in the `onMessageReceived` callback to receive messages. We recommend you to call the `notifyReceive` function when the `onMessageReceived` callback is called to enable tracking of the notification reception on the mobile device. In Adobe Campaign this is named **print** notification: this function should be called just before requesting the OS to display the notification.

    YourApplicationMessagingService.java
    
    ```
    package com.android.YourApplication;
 
    import android.content.Context;
    import android.content.SharedPreferences;
    import android.os.Bundle;
    import android.util.Log;
    
    import com.google.firebase.messaging.FirebaseMessagingService;
    import com.google.firebase.messaging.RemoteMessage;
    
    import java.util.Iterator;
    import java.util.Map;
    import java.util.Map.Entry;
    
    public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService 
        {
        private static final String TAG = "MyFirebaseMsgService";
 
        @Override
        public void onMessageReceived(RemoteMessage message) 
            {
            Log.d(TAG, "Receive message from: " + message.getFrom());
            Map<String,String> payloadData = message.getData();
            final Bundle extras = new Bundle();
            final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
            while(iter.hasNext())
            {
            final Entry<String, String>  entry =iter.next();
            extras.putString(entry.getKey(), entry.getValue());
            }
 
            SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
            String mesg = payloadData.get("_msg");
            String title = payloadData.get("title");
            String url = payloadData.get("url");
            String messageId = payloadData.get("_mId");
            String deliveryId = payloadData.get("_dId");
            YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
            }
        }   
    ```

    For Campaign Android SDK v1.1.1

    ```
    public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras)
    {
        if( message == null ) message = "No Content";
        if( title == null )   title = "No title";
        if( url == null )     url = "http://www.tripadvisor.fr";
        int iconId = R.drawable.notif_neotrip;
    
        // notify Adobe Campaign that a notification just arrived
        SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
        Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
        Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
        Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
 
        NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
        nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
        public void onNeolaneException(NeolaneException arg0, Object arg1) {}
        public void onIOException(IOException arg0, Object arg1) {}
        public void onComplete(String arg0, Object arg1){}
        });
        if (yourApplication.isActivityVisible())
        {
        Log.i("INFO", "The application has the focus" );
        ...
        }
        else
        {
        // notification creation
        NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
        Notification notification;
    
        // Activity to start
        Intent notifIntent = new Intent(context.getApplicationContext(), NotificationActivity.class);
        notifIntent.putExtra("notificationText", message);
        notifIntent.putExtra(NotificationActivity.NOTIFICATION_URL_KEYNAME, url);
        notifIntent.putExtra("_dId", deliveryId);
        notifIntent.putExtra("_mId", messageId);
        notifIntent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
        PendingIntent contentIntent = PendingIntent.getActivity(context, 1, notifIntent, PendingIntent.FLAG_UPDATE_CURRENT);
    
        notification = new Notification.Builder(context)
                .setContentTitle(title)
                .setContentText(message)
                .setSmallIcon(iconId)
                .setContentIntent(contentIntent)
                .build();
    
        // launch the notification
        notification.flags |= Notification.FLAG_AUTO_CANCEL;
        notificationManager.notify(1234, notification);
        }
    }
    ```

1. **Track opens of data messages**

    For data messages, you can track when a user clicks on a notification to open it, using the `notifyOpening` function. The notification activity will be created when user clicks on the notification (created during `onMessageReceived`function call)

    For Campaign Android SDK v1.1.1

    ```
    public class NotificationActivity extends Activity {
        public void onCreate(Bundle savedBundle) {
            [...]
            Bundle extra = getIntent().getExtras();
            if (extra != null) {
                // reinit the Campaign sdk
                SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
                Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
                Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));               
                Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
            
                // Get the messageId and the deliveryId to perform tracking
                String deliveryId = extra.getString("_dId");
                String messageId = extra.getString("_mId");
                
                if (deliveryId != null && messageId != null) 
                {
                    try {
                    Neolane.getInstance().notifyOpening(messageId, Integer.valueOf(deliveryId));
                    } catch (NeolaneException e) {
                    // ...
                    } catch (IOException e) {
                    // ...
                    }
                }
            }
        }
    }

1. **Track opens and clicks on notification messages**

    For notification messages, the open/click tracking needs to be done with the `notifyOpening` function inside the application launch activity, as below:
    ```
    /** Called when the activity is first created. */
        @Override
        public void onCreate(Bundle savedInstanceState)
        {
        super.onCreate(savedInstanceState);
    
        SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
    
        // initialize Neolane sdk
        Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
        Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
        Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
        ...
        ...
        ...

            // Manage opening/receive tracking of message notification
            Intent intent = getIntent();
            Bundle data = intent.getExtras();
            String messageId = null, deliveryId = null;
            if( data != null ) {
            if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
            if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
            if ( messageId != null && deliveryId != null) {
                Log.i(TAG, "Notify opening from backgroun click_action");
                NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
                nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
                public void onNeolaneException(NeolaneException arg0, Object arg1) {
                    toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
                }
                public void onIOException(IOException arg0, Object arg1) {
                    toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
                }
                public void onComplete(String arg0, Object arg1) {
                    toastMessage( "error", getString(R.string.open_track_ok));
                }
                });
                nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
                public void onNeolaneException(NeolaneException arg0, Object arg1) {
                    toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
                }
                public void onIOException(IOException arg0, Object arg1) {
                    toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
                }
                public void onComplete(String arg0, Object arg1) {
                    toastMessage( "error", getString(R.string.rec_track_ok));
                }
                });
            }
            }
        }
    ```

  >[!NOTE]
  >
  > Similar management needs to be done if user is using `click_action` option inside the targeted activity.

1. **Receive tracking for data messages**

    For data messages, the tracking is received at `onMessageReceived` call level. The 'notifyReceive' function needs to be called.

    YourApplicationMessagingService.java

    ```
    package com.android.YourApplication;
    
    import android.content.Context;
    import android.content.SharedPreferences;
    import android.os.Bundle;
    import android.util.Log;
    
    import com.google.firebase.messaging.FirebaseMessagingService;
    import com.google.firebase.messaging.RemoteMessage;
    
    import java.util.Iterator;
    import java.util.Map;
    import java.util.Map.Entry;
    
 
    public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService {
    private static final String TAG = "MyFirebaseMsgService";
    
    @Override
    public void onMessageReceived(RemoteMessage message) 
        {
            Log.d(TAG, "Receive message from: " + message.getFrom());
            Map<String,String> payloadData = message.getData();
            final Bundle extras = new Bundle();
            final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
            while(iter.hasNext())
            {
            final Entry<String, String>  entry =iter.next();
            extras.putString(entry.getKey(), entry.getValue());
            }
        
            SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
            String mesg = payloadData.get("_msg");
            String title = payloadData.get("title");
            String url = payloadData.get("url");
            String messageId = payloadData.get("_mId");
            String deliveryId = payloadData.get("_dId");
            YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
        }
    }
    ```

    ```
    public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras){
        .....
        .....
            // notify Neolane that a notification just arrived
            SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
            Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
            Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
            Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
        
            NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
            nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
                public void onNeolaneException(NeolaneException arg0, Object arg1) {}
                public void onIOException(IOException arg0, Object arg1) {}
                public void onComplete(String arg0, Object arg1){}
        });
    }
    ```

1. **Receive tracking for notification messages**

    For notification messages, the tracking reception must be configured at two level:

    * `onMessageReceived` (application not in the background): the implementation has been done in the previous section
    * `onCreate` of the launch activity (or the targeted activity if `click_action`function is used.) (Application not in backgound).
    
    It needs to be done at the same moment as open/click tracking.

    ```
    /** Called when the activity is first created. */
        @Override
        public void onCreate(Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
        
            SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
        
            // initialize Neolane sdk
            Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
            Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
            Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
    ...
    ...
    ...
    
        // Manage opening/receive tracking of message notification
        Intent intent = getIntent();
        Bundle data = intent.getExtras();
        String messageId = null, deliveryId = null;
        if( data != null ) {
        if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
        if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
        if ( messageId != null && deliveryId != null) {
            Log.i(TAG, "Notify opening from backgroun click_action");
            NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
            nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
            public void onNeolaneException(NeolaneException arg0, Object arg1) {
                toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
            }
            public void onIOException(IOException arg0, Object arg1) {
                toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
            }
            public void onComplete(String arg0, Object arg1) {
                toastMessage( "error", getString(R.string.open_track_ok));
            }
            });
            nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
            public void onNeolaneException(NeolaneException arg0, Object arg1) {
                toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
            }
            public void onIOException(IOException arg0, Object arg1) {
                toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
            }
            public void onComplete(String arg0, Object arg1) {
                toastMessage( "error", getString(R.string.rec_track_ok));
            }
            });
        }
        }
    }
    ```




## Integrate iOS SDK

1. **Register the mobile device to Adobe Campaign server**

    The registration function enables you to:

    * send the notification ID or push ID (deviceToken for iOS and registrationID for Android) to Adobe Campaign.
    * recover the reconciliation key or userKey (email or account number, for instance)
    
    
    ```
    // Callback called on successful registration to the APNs
     - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
    {
      // Pass the token to Adobe Campaign
      Neolane_SDK *nl = [Neolane_SDK getInstance];
      [nl registerDevice:tokenString:self.userKey:dic];
    }
    ```

1. **Enable tracking function**

  The tracking function allows you to track when notifications are activated (opens).

  ```
  (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
  fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
  {
  if( launchOptions ) { // Retrieve notification parameters here ... // Track application opening Neolane_SDK
  *nl = [Neolane_SDK getInstance]; [nl track:launchOptions:NL_TRACK_CLICK]; } 
  ...  
  completionHandler(UIBackgroundFetchResultNoData);
  }
  ```

1. **Silent notification tracking**

    iOS lets you send silent notifications, a notification or data which will be directly sent to a mobile application without displaying it. Adobe Campaign allows you to track them.

    To track your silent notification, follow the example below:

    ```
    // AppDelegate.m
    ...
    ...
    #import "AppDelegate.h"
    #import "Neolane_SDK.h"
    ...
    ...
    // Callback called when the application is already launched (whether the application is running foreground or background)
    - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
    {
    NSLog(@"IN didReceiveRemoteNotification:fetchCompletionHandler");
    if (launchOptions) NSLog(@"IN launchOptions: %@", [launchOptions description]);
    NSLog(@"Application state: %ld", (long)application.applicationState);

    // Silent Notification (specific case, can use NL_TRACK_RECEIVE as the user doesn't have click/open the notification)
    if ([launchOptions[@"aps"][@"content-available"] intValue] == 1 )
        {
    NSLog(@"Silent Push Notification");
    ...  
    ...
    //Call receive tracking
            Neolane_SDK *nl = [Neolane_SDK getInstance];
    [nl track:launchOptions:NL_TRACK_RECEIVE];

    completionHandler(UIBackgroundFetchResultNoData); //Do not show notification
    return;
    }  
    ...
    ...
            completionHandler(UIBackgroundFetchResultNoData);
    }
    ```

1. Configure registration status

    The delegate protocol allows you to get the result of the **registerDevice** call and can be used to know if an error occured during registration.

    The **registerDeviceStatus** prototype is:

    ```
    - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
    ```

    * **Status** allows you to know if a registration succeeded or if an error occured.

    * **ErrorReason** provides you with more information on the errors that occurred. For more information on available errors and their descriptions, refer to the table below.

    <table> 
    <thead>
    <tr>
    <th> Status<br /> </th>
    <th> Description<br /> </th>
    <th> ErrorReason<br /> </th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td> ACCRegisterDeviceStatusSuccess <br /> </td>
    <td> Registration Succeeded<br /> </td>
    <td> EMPTY<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty <br /> </td>
    <td> The ACC marketing server hostname is empty or not set.<br /> </td>
    <td> EMPTY<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureIntegrationKeyEmpty <br /> </td>
    <td> The integration key is empty or not set.<br /> </td>
    <td> EMPTY<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureConnectionIssue<br /> </td>
    <td> Connection issue with ACC<br /> </td>
    <td> More information (in OS current language)<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureUnknownUUID<br /> </td>
    <td> The provided UUID (integration key) is unknown.<br /> </td>
    <td> EMPTY<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureUnexpectedError<br /> </td>
    <td> Unexpected error returned to ACC server.<br /> </td>
    <td> The error message returned to ACC.<br /> </td>
    </tr>
    </tbody>
    </table>

    **Neolane_SDKDelegate** protocol and **registerDeviceStatus** delegate definition is as follows:

    ```
    //  Neolane_SDK.h
    //  Neolane SDK
    ..
    .. 
    // Register Device Status Enum
    typedef NS_ENUM(NSUInteger, ACCRegisterDeviceStatus) {
    ACCRegisterDeviceStatusSuccess,                               // Resistration Succeed
    ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty,   // The Campaign marketing server hostname is Empty or not set
    ACCRegisterDeviceStatusFailureIntegrationKeyEmpty,            // The integration key is empty or not set
    ACCRegisterDeviceStatusFailureConnectionIssue,                // Connection issue with Campaign, more information in errorReason
    ACCRegisterDeviceStatusFailureUnknownUUID,                    // The provided UUID (integration key) is unknown
    ACCRegisterDeviceStatusFailureUnexpectedError                 // Unexpected error returned by Campaign server, more information in errorReason
    };
    // define the protocol for the registerDeviceStatus delegate
    @protocol Neolane_SDKDelegate <NSObject>
    @optional
    - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status :(NSString *) errorReason;
    @end
    @interface Neolane_SDK: NSObject {
    } 
    ...
    ...
    // registerDeviceStatus delegate
    @property (nonatomic, weak) id <Neolane_SDKDelegate> delegate;
    ...
    ...
    @end
    ```

    To implement **registerDeviceStatus** delegate, follow these steps:

    1. Implement the **setDelegate** during the SDK initialization.

        ```
        // AppDelegate.m
        ...
        ... 
        - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
        {
        ...
        ...
            // Get the stored settings

            NSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];
            NSString *strMktHost = [defaults objectForKey:@"mktHost"];
            NSString *strTckHost = [defaults objectForKey:@"tckHost"];
            NSString *strIntegrationKey = [defaults objectForKey:@"integrationKey"];
            userKey = [defaults objectForKey:@"userKey"];

            // Configure Neolane SDK on first launch
            Neolane_SDK *nl = [Neolane_SDK getInstance];
            [nl setMarketingHost:strMktHost];
            [nl setTrackingHost:strTckHost];
            [nl setIntegrationKey:strIntegrationKey];
            [nl setDelegate:self];    // HERE
        ...
        ...
        }
        ```

    1. Add the protocol in the **@interface** of your class.

        ```
        //  AppDelegate.h

        #import <UIKit/UIKit.h>
        #import <CoreLocation/CoreLocation.h>
        #import "Neolane_SDK.h"

        @class LandingPageViewController;

        @interface AppDelegate : UIResponder <UIApplicationDelegate, CLLocationManagerDelegate, Neolane_SDKDelegate> {
            CLLocationManager *locationManager;
            NSString *userKey;
            NSString *mktServerUrl;
            NSString *tckServerUrl;
            NSString *homeURL;
            NSString *strLandingPageUrl;
            NSTimer *timer;
        }
        ```

    1. Implement the delegate in the **AppDelegate**.

        ```
        //  AppDelegate.m

        #import "AppDelegate.h"
        #import "Neolane_SDK.h"
        #import "LandingPageViewController.h"
        #import "RootViewController.h"
        ...
        ...
        - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status :(NSString *) errorReason
        {
            NSLog(@"registerStatus: %lu",status);

            if ( errorReason != nil )
                NSLog(@"errorReason: %@",errorReason);

            if( status == ACCRegisterDeviceStatusSuccess )
            {
                // Registration successful
                ...
                ...
            }
            else { // An error occurred
                NSString *message;
                switch ( status ){
                    case ACCRegisterDeviceStatusFailureUnknownUUID:
                        message = @"Unkown IntegrationKey (UUID)";
                        break;
                    case ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty:
                        message = @"Marketing URL not set or Empty";
                        break;
                    case ACCRegisterDeviceStatusFailureIntegrationKeyEmpty:
                        message = @"Integration Key not set or empty";
                        break;
                    case ACCRegisterDeviceStatusFailureConnectionIssue:
                        message = [NSString stringWithFormat:@"%@ %@",@"Connection issue:",errorReason];
                        break;
                    case ACCRegisterDeviceStatusFailureUnexpectedError:
                    default:
                        message = [NSString stringWithFormat:@"%@ %@",@"Unexpected Error",errorReason];
                        break;
                }
            ...
            ...
            }
        }
        @end
        ```

## Variables {#variables}

The variables let you define mobile application behavior after receiving a notification. These variables must be defined in the mobile application code and in the Adobe Campaign console, in the **[!UICONTROL Variables]** tab in the dedicated mobile application service. 

[!DNL :arrow_upper_right:] Learn more in **Campaign Classic v7 documentation** on mobile app: [Configuration steps for iOS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html) and [Configuration steps for Andoid](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html). 

Below is an example of a code that allows a mobile application to collect any added variables in a notification. In our example, we are using the "VAR" variable.

* **In Android**:

  ```
  public void onReceive(Context context, Intent intent) {
       ...
      String event = intent.getStringExtra("VAR");
       ...
  }
  ```

* **In iOS**:

  ```
  - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
  {
      ....
      if( launchOptions )
      {
          // When application is not already launched, the notification data if any are stored in the key 'UIApplicationLaunchOptionsRemoteNotificationKey'
          NSDictionary *localLaunchOptions = [launchOptions objectForKey:@"UIApplicationLaunchOptionsRemoteNotificationKey"];
          if( localLaunchOptions )
          {
           ...
           [localLaunchOptions objectForKey:@"VAR"];
          ...
          }
     }
  }

  // Callback called when the application is already launched (whether the application is running foreground or background)
  - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
  {
      if( launchOptions )
      {
       ...
          [launchOptions objectForKey:@"VAR"];
      }
  }
  ```

>[!CAUTION]
>
>Adobe recommends choosing short variable names because notification size is limited to 4kB for iOS and Android.

## Notification Service Extension {#notification-service-extension}

**For iOS**

The media has to be downloaded at the notification service extension level.

```

#import "NotificationService.h"

@interface NotificationService ()

@property (nonatomic, strong) void (^contentHandler)(UNNotificationContent *contentToDeliver);
@property (nonatomic, strong) UNMutableNotificationContent *bestAttemptContent;

@end

@implementation NotificationService

- (void)didReceiveNotificationRequest:(UNNotificationRequest *)request withContentHandler:(void (^)(UNNotificationContent * _Nonnull))contentHandler {
    NSDictionary *userInfo = nil;
    NSString *url = nil;

    self.contentHandler = contentHandler;
    self.bestAttemptContent = [request.content mutableCopy];

    userInfo = request.content.userInfo;
    if ( userInfo != nil )
    {
        url = userInfo[@"mediaUrl"];  // Get the url of the media to download (Adobe Campaign additional variable)
    }
    ...
    // Perform the download to local storage

```

## Notification Content Extension {#notification-content-extension}

**For iOS**

At this level, you need to:

* Associate your content extension to the category sent by Adobe Campaign:

  If you want your mobile application to display an image, you can set the category value to "image" in Adobe Campaign and in your mobile application, you create a notification extension with the **UNNotificationExtensionCategory** parameter set to "image". When the push notification is received on the device, the extension is called according to the defined category value.

* Define your notification layout

  You need to define a layout with the relevant widgets. For an image, the widget is named **UIImageView**.

* Display your media

  You need to add code to feed the media data to the widget. Here is an example of code for an image:

  ```

  #import "NotificationViewController.h"
  #import <UserNotifications/UserNotifications.h>
  #import <UserNotificationsUI/UserNotificationsUI.h>

  @interface NotificationViewController () <UNNotificationContentExtension>
  
  @property (strong, nonatomic) IBOutlet UIImageView *imageView;
  @property (strong, nonatomic) IBOutlet UILabel *notifContent;
  @property (strong, nonatomic) IBOutlet UILabel *label;
  
  @end

  @implementation NotificationViewController

  - (void)viewDidLoad {
      [super viewDidLoad];
      // Do any required interface initialization here.
  }

  - (void)didReceiveNotification:(UNNotification *)notification {
      self.label.text = notification.request.content.title;
      self.notifContent.text = notification.request.content.body;
      UNNotificationAttachment *attachment = [notification.request.content.attachments objectAtIndex:0];
      if ([attachment.URL startAccessingSecurityScopedResource])
      {
        NSData * imageData = [[NSData alloc] initWithContentsOfURL:attachment.URL];
        self.imageView.image =[UIImage imageWithData: imageData];
        [attachment.URL stopAccessingSecurityScopedResource];
      }
  }
  @end
  
  ```
