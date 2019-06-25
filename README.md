# Multi-Process Sample

This node-js app has two processes, a `web` and a `worker`.  These are defined in the `Procfile`.

The `web` process prints a message based on the path you give it:

```
curl <multi-process-app>/bananas

Hi, I love bananas!
```

The `worker` process calculates the Fibonacci sequence and logs it to stdout.

This repository includes a `manifest.yml` that will scale the `web` process to 1 instance
and the `worker` process to 2 instances.

In the logs for the app, you will see messages from both processes interleaved, i.e.:
```
... [APP/PROC/WORKER/0] OUT Calculating the Fibonacci sequence...
... [APP/PROC/WORKER/0] OUT 1
... [APP/PROC/WEB/0] OUT Server running at http://0.0.0.0:8080/
... [APP/PROC/WORKER/0] OUT 1
... [APP/PROC/WORKER/0] OUT 2
... [APP/PROC/WORKER/0] OUT 3
```
