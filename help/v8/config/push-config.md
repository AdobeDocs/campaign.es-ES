---
product: Adobe Campaign
title: Integración de los SDK de Campaign con la aplicación
description: Obtenga información sobre cómo integrar los SDK para iOS y Android de Campaign con su aplicación
version: v8
feature: Push
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: ee0ea4c1e086ee579e63e391683cc8e896d09f0b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Integración de los SDK de Campaign con la aplicación {#integrate-campaign-sdk}

Utilice los SDK de Campaign para iOS y Android para facilitar la integración de la aplicación móvil en la plataforma Adobe Campaign.

Las versiones compatibles con Android e iOS, así como las versiones compatibles con los SDK de Campaign para Campaign v8, se enumeran en la [Matriz de compatibilidad](../start/compatibility-matrix.md#MobileSDK) .

>[!NOTE]
>
>Como administrador de Campaign, puede descargar los SDK de Campaign desde [Experience Cloud Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). Para obtener más información, póngase en contacto con [Adobe Customer Care](https://helpx.adobe.com/es/enterprise/admin-guide.html).


## Declarar la configuración de integración {#declaring-integration-settings}

Para integrar el SDK de Campaign en la aplicación móvil, el administrador funcional debe proporcionar la siguiente información al desarrollador:

* **Una clave de integración**: para permitir a la plataforma Adobe Campaign identificar la aplicación móvil.

   >[!NOTE]
   >
   >Esta clave de integración se introduce en la consola de Adobe Campaign, en la pestaña **[!UICONTROL Information]** del servicio dedicado a la aplicación móvil. Consulte la [documentación del Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app).

* **Una URL de seguimiento**: coincide con la dirección del servidor de rastreo de Adobe Campaign.
* **Una URL de marketing**: para habilitar la recopilación de suscripciones.

* **En Android**:

   ```
   Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
   Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
   Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
   ```

* **En iOS**:

   ```
   Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl setMarketingHost:strMktHost];
   [nl setTrackingHost:strTckHost];
   [nl setIntegrationKey:strIntegrationKey];
   ```

## Integración del SDK para Android

Android SDK es una biblioteca jar escrita en JAVA. Permite a los desarrolladores de Android integrarse con Adobe Campaign: registre un dispositivo nuevo, vincule el dispositivo con un usuario, realice un seguimiento del comportamiento y mucho más.

En esta sección, aprenda a utilizar el SDK para Android en una aplicación de Android que implementa [Google Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging/).

### Configurar FCM

Para utilizar la notificación push en Android, debe tener una cuenta de FCM, configurar la aplicación de Android para recibir la notificación y vincular la aplicación a la cuenta de FCM. Obtenga más información en [Documentación de Google](https://firebase.google.com/docs/cloud-messaging/).

Consulte la [Documentación de Google](https://firebase.google.com/docs/android/setup) para agregar Firebase al proyecto de Android.

Obtenga información sobre cómo implementar FCM en la aplicación en [Documentación de Google](https://firebase.google.com/docs/android/setup).

>[!NOTE]
>
> * No olvide descargar y agregar google-services.json a su proyecto.
   >
   > 
* El `apiKey` debe coincidir con el `projectKey` configurado en la aplicación móvil de Adobe Campaign vinculada a esta aplicación Android.


### Configuración del SDK para Android

1. **Inicialización del SDK**

   Antes de utilizar el SDK para Android, debe inicializarlo. La inicialización del SDK se puede realizar en la función `onCreate` de una actividad.

   ```
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       // initialize Campaign SDK
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       Neolane.getInstance().setIntegrationKey(settings.getString(YourApplicationActivity.APPUUID_NAME, YourApplicationActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(YourApplicationActivity.SOAPRT_NAME, YourApplicationActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(YourApplicationActivity.TRACKRT_NAME, YourApplicationActivity.DFT_TRACKRT));
       ...
   }
   ```

   El `IntegrationKey` debe coincidir con el &quot;IntegrationKey&quot; configurado en la aplicación móvil de Adobe Campaign vinculada a esta aplicación Android.

1. **Registro del dispositivo móvil en el servidor de Adobe Campaign**

   La función de registro le permite:

   * Enviar la ID de notificación o ID remota a Adobe Campaign (token de dispositivo en iOS e ID de registro en Android).
   * Recuperación de la clave de reconciliación o clave de usuario userKey (por ejemplo, correo electrónico o número de cuenta).

   Debe registrar el dispositivo en Adobe Campaign, en la inicialización de la aplicación o en la acción del usuario. Se puede hacer fácilmente con el método `registerDevice`.

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
       // Campaign Registration
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

1. **Notificar a Campaign cuando cambie el token de dispositivo móvil del usuario**

   Se recomienda utilizar la función `registerDevice` al llamar a la función `onTokenRefresh` para notificar a Adobe Campaign del cambio en el token del dispositivo móvil del usuario.

   Por ejemplo:

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

1. **Configurar el servicio de Firebase Messaging**

   Amplíe `FirebaseMessagingService` en la llamada de retorno `onMessageReceived` para recibir mensajes. Le recomendamos que llame a la función `notifyReceive` cuando se llame a la rellamada `onMessageReceived` para habilitar el seguimiento de la recepción de notificaciones en el dispositivo móvil. En Adobe Campaign, esto se denomina **print** notification: se debe llamar a esta función justo antes de solicitar al sistema operativo que muestre la notificación.

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

   Para el SDK v1.1.1 de Android de Campaign

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

1. **Seguimiento de aperturas de mensajes de datos**

   En el caso de los mensajes de datos, se puede realizar un seguimiento de cuándo un usuario hace clic en una notificación para abrirla mediante la función `notifyOpening`. La actividad de notificación se creará cuando el usuario haga clic en la notificación (creada durante la `onMessageReceived`llamada a la función)

   Para el SDK v1.1.1 de Android de Campaign

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
   
1. **Seguimiento de aperturas y clics en mensajes de notificación**

   Para los mensajes de notificación, el rastreo de aperturas/clics debe realizarse con la función `notifyOpening` dentro de la actividad de inicio de la aplicación, como se muestra a continuación:

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
> Es necesario realizar una administración similar si el usuario utiliza la opción `click_action` dentro de la actividad de destino.


1. **Recibir seguimiento de mensajes de datos**

   Para los mensajes de datos, el seguimiento se recibe en el nivel de llamada `onMessageReceived` . Se debe llamar a la función &quot;notifyReceive&quot;.

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
           // notify Campaign that a notification just arrived
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

1. **Recibir seguimiento de mensajes de notificación**

   Para los mensajes de notificación, la recepción del seguimiento debe configurarse en dos niveles:

   * `onMessageReceived` (la aplicación no está en segundo plano): la implementación se ha realizado en la sección anterior
   * `onCreate` de la actividad de lanzamiento (o la actividad de destino si se utiliza la  `click_action`función ). (La aplicación no está en segundo plano).

   Debe realizarse en el mismo momento que el seguimiento de aperturas/clics.

   ```
   /** Called when the activity is first created. */
       @Override
       public void onCreate(Bundle savedInstanceState)
       {
           super.onCreate(savedInstanceState);
   
           SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
           // initialize Campaign SDK
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


## Integración del SDK de iOS

1. **Registro del dispositivo móvil en el servidor de Adobe Campaign**

   La función de registro le permite:

   * Enviar la ID de notificación o ID remota a Adobe Campaign (token de dispositivo en iOS e ID de registro en Android).
   * Recuperación de la clave de reconciliación o clave de usuario userKey (por ejemplo, correo electrónico o número de cuenta).

   ```
   // Callback called on successful registration to the APNs
    - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
   {
     // Pass the token to Adobe Campaign
     Neolane_SDK *nl = [Neolane_SDK getInstance];
     [nl registerDevice:tokenString:self.userKey:dic];
   }
   ```

1. **Habilitar la función de seguimiento**

La función de seguimiento permite rastrear cuándo se activan las notificaciones (aperturas).

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

1. **Seguimiento de notificaciones silenciosas**

   iOS permite enviar notificaciones silenciosas, una notificación o datos que se envían directamente a una aplicación móvil sin mostrarlo. Adobe Campaign permite rastrearlas.

   Para rastrear una notificación silenciosa, siga el ejemplo a continuación:

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

1. Configuración del estado de registro

   El protocolo delegado permite obtener el resultado de la llamada **registerDevice** y se puede utilizar para saber si se ha producido un error durante el registro.

   El prototipo de **registerDeviceStatus** es:

   ```
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
   ```

   * **Status** permite saber si un registro se ha realizado correctamente o si se ha producido un error.

   * **ErrorReason** proporciona más información sobre los errores que se han producido. Para obtener más información sobre los errores disponibles y sus descripciones, consulte la tabla siguiente.

   <table> 
    <thead>
    <tr>
    <th> Estado<br /> </th>
    <th> Descripción<br /> </th>
    <th> ErrorReason<br /> </th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td> ACCRegisterDeviceStatusSuccess <br /> </td>
    <td> Registro con éxito<br /> </td>
    <td> VACÍO<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty <br /> </td>
    <td> El nombre de anfitrión del servidor de marketing ACC está vacío o no se ha definido.<br /> </td>
    <td> VACÍO<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureIntegrationKeyEmpty <br /> </td>
    <td> La clave de integración está vacía o no se ha definido.<br /> </td>
    <td> VACÍO<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureConnectionIssue<br /> </td>
    <td> Problema de conexión con ACC<br /> </td>
    <td> Más información (en el idioma actual de OS)<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureUnknownUUID<br /> </td>
    <td> Se desconoce la UUID (clave de integración) proporcionada.<br /> </td>
    <td> VACÍO<br /> </td>
    </tr>
    <tr> 
    <td> ACCRegisterDeviceStatusFailureUnexpectedError<br /> </td>
    <td> Error inesperado devuelto al servidor ACC.<br /> </td>
    <td> El mensaje de error devuelto a ACC.<br /> </td>
    </tr>
    </tbody>
    </table>

   El protocolo **Neolane_SDKDelegate** y la definición delegada **registerDeviceStatus** son las siguientes:

   ```
   //  Neolane_SDK.h
   //  Campaign SDK
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

   Para implementar el delegado **registerDeviceStatus**, siga estos pasos:

   1. Implemente **setDelegate** durante la inicialización del SDK.

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
      
          // Configure Campaign SDK on first launch
          Neolane_SDK *nl = [Neolane_SDK getInstance];
          [nl setMarketingHost:strMktHost];
          [nl setTrackingHost:strTckHost];
          [nl setIntegrationKey:strIntegrationKey];
          [nl setDelegate:self];    // HERE
      ...
      ...
      }
      ```

   1. Añada el protocolo en la **@interface** de su clase.

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

   1. Implemente el delegado en **AppDelegate**.

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

Las variables permiten definir el comportamiento de la aplicación móvil después de recibir una notificación. Estas variables deben definirse en el código de la aplicación móvil y en la consola de Adobe Campaign, en la pestaña **[!UICONTROL Variables]** del servicio dedicado de la aplicación móvil.

[!DNL :arrow_upper_right:] Obtenga más información en la  **documentación de** Campaign Classic v7 sobre la aplicación móvil:  [Pasos de configuración para ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html) iOSy pasos de  [configuración para Android](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

A continuación, se muestra un ejemplo de código que permite a una aplicación móvil recopilar variables añadidas en una notificación. En este ejemplo, se utiliza la variable “VAR”.

* **En Android**:

   ```
   public void onReceive(Context context, Intent intent) {
        ...
       String event = intent.getStringExtra("VAR");
        ...
   }
   ```

* **En iOS**:

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
>Adobe recomienda elegir nombres de variables cortos debido a que el tamaño de notificación está limitado a 4 kB para iOS y Android.

## Extensión de servicio de notificaciones {#notification-service-extension}

**Para iOS**

Los medios deben descargarse en el nivel de extensión del servicio de notificación.

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

## Extensión de contenido de notificación {#notification-content-extension}

**Para iOS**

A este nivel, es necesario:

* Asocie la extensión de contenido a la categoría enviada por Adobe Campaign:

   Si desea que la aplicación móvil muestre una imagen, puede establecer el valor de la categoría en “imagen” en Adobe Campaign y crear en la aplicación móvil una extensión de notificación con el parámetro **UNNotificationExtensionCategory** establecido en “imagen”. Cuando se recibe la notificación push en el dispositivo, se llama a la extensión según el valor de categoría definido.

* Definición del diseño de la notificación

   Se debe definir el diseño con elementos gráficos relevantes. Para una imagen, el elemento gráfico se denomina **UIImageView**.

* Visualización de sus medios

   Se debe añadir código para enviar los datos de medios al widget. A continuación, se muestra un ejemplo de código para una imagen:

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
