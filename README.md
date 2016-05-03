**SockJs Client for Android**

*Usage:*

      public class MainActivity extends AppCompatActivity implements SockJsClientListener{
          SockJsClient sockJsClient;
          @Override
          protected void onCreate(Bundle savedInstanceState) {
              super.onCreate(savedInstanceState);
              setContentView(R.layout.activity_main);
              sockJsClient = new SockJsClient(this);
              sockJsClient.connectSockJs("url", "accessKey");
          }
          @Override
          public void onOpen(String json) {
              Log.d("open", json);
          }
      
          @Override
          public void onSuccess(String json) {
              //To do if response having json, parse json here...
              Log.d("success", json);
          }
      
          @Override
          public void onError(String json) {
              Log.d("error", json);
          }
      
          @Override
          public void onClose(String json) {
              Log.d("close", json);
          }
          
          
          @Override
          protected void onStop() {
              sockJsClient.disconnectSockJs();
              super.onStop();
          }
      
          @Override
          protected void onStart() {
              //To do Here connect sockjs again...
              //sockJsClient.connectSockJs("url", "accessKey");
          }
      }
          
  *Download:*
  
        dependencies {
            compile 'com.vishu.sockjsclientandroid:sockjsandroidclient:1.0.1'
        }
