# Asynch
Android 中线程之间通信的多种方式AsyncTask、IntentService、HandlerThread，RxJava，runOnUiThread
* Asynctask   a创建AsyncTask子类的实例对象（即 任务实例） b. 同一个AsyncTask实例对象只能执行1次，若执行第2次将会抛出异常  c. 执行任务中，系统会自动调用AsyncTask的一系列方法：onPreExecute() 、doInBackground()、onProgressUpdate() 、onPostExecute()
* Handler 最简单的使用Handler完成子线程和主线程的通信（子线程发消息给主线程） 注：1.子线程异步通知主线程刷新UI  2.主线程通知子线程通信方式 
handler 两种发送消息方式  handler.post(Runnabel)/handler.post(Runnable,1000)
* Rxjava 是目前比较流行的异步操作，经常用户网络请求回调  原理主要是订阅关系，线程切换，它以数据流回调
* runOnUiThread  Runnable对像就能在ui程序中被调用。如果当前线程是UI线程，那么行动是立即执行,果当前线程不是UI线程,操作是发布到事件队列的UI线程
* IntentService是继承于Service并处理异步请求的一个类，在IntentService内有一个工作线程来处理耗时操作，
启动IntentService的方式和启动传统Service一样，同时，当任务执行完后，IntentService会自动停止，而不需要我们去手动控制。
另外，可以启动IntentService多次，而每一个耗时操作会以工作队列的方式在IntentService的onHandleIntent回调方法中执行，并且，
每次只会执行一个工作线程，执行完第一个再执行第二个，以此类推

AsyncTask, IntentService, HandlerThread, RxJava, runOnUiThread
* Asynctask a creates an instance object of Asynctask subclass (i.e. task instance) b. the same Asynctask instance object can only execute once, and the second execution will throw an exception c. during execution, the system will automatically call a series of methods of Asynctask: onPreExecute(), doInBackground(), onProgressUpdate(), onPostExecute()
* Handler is the simplest way to use Handler to complete the communication between the child thread and the main thread (the child thread sends a message to the main thread). Note: 1. The child thread asynchronously informs the main thread to refresh the UI
Handler two ways to send messages handler. Post (Runnabel)/handler. Post (Runnable,1000)
* Rxjava is a popular asynchronous operation, often the user network request callback principle is mainly subscription relationship, thread switch, it to the data flow callback
* runOnUiThread Runnable object can be called in the UI program.If the current thread is a UI thread, the action is executed immediately. If the current thread is not a UI thread, the action is the UI thread published to the event queue
* IntentService is a class that inherits from the Service and handles asynchronous requests. Within the IntentService, there is a worker thread to handle time-consuming operations.
IntentService is started in the same way as traditional services, and when the task is finished, the IntentService will automatically stop without manual control.
In addition, IntentService can be started multiple times, and each time-consuming operation is performed as a work queue in IntentService's onHandleIntent callback method, and,
Only one worker thread executes at a time, the first one executes the second, and so on
