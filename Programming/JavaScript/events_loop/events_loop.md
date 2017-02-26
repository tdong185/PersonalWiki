## Events Loop [Back](./../JavaScript.md)

The multi-threading technology has given us a way to handle works that may take much more time to complete. However, Node.js and V8 has not provided us a way to create a new thread in our programming. Even so, the APIs of C++ have given a way to do this and what it means is that when you are doing some non-blocking tasks, Node.js has potentially created a thread to handle these tasks. Once the thread complete the task, the thread will automatically execute your callback functions which are given before.

In brief, when you calling `setTimeout`, `http.get`, or `fs.readFile`, Node.js will deliver these tasks to another potential thread to do so, so that it can continue to execute other codes. Generally, these functions will also accept a callback function to call after completing the tasks you set before. When tasks are running, these callback functions will be stored in a queue, named **Tasks Queue**, to wait for recalling