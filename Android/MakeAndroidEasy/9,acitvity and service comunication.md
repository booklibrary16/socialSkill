1，猜想：      
 class DownloadBinder extends Binder {    


    private ServiceConnection connection = new ServiceConnection() {
当Activity通过调用bindService(Intent service, ServiceConnection conn,int flags),     
通过bingder来进行访问数据，
