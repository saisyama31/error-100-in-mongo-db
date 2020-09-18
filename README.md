i want to elaborate the issues i got while installing mongodb community server(zip file not msi)
## this issue is only for windows user

1) i installed mongodb community server for working on my database and i created two folders in c drive in-> user folder -> creted my name folder and added -> two folders named mongodb(i renamed it which is mongodb community server) and mongodb-data for database.
i typed this command on powershell :: /Users/sai/mongodb/bin/mongod.exe --dbpath=/Users/sai/mongodb-data
and i didn't get any error and extra-files in my my mongo-db folder(error pic::https://github.com/saisyama31/error-100-in-mongo-db/blob/master/extra%20files%20and%20folder.png)

#solution for the above issue
1) did a little digging and it seems that dll belongs to Microsoft Visual C ++ Redistributable. I'd recommend download and installing the latest Visual C++ from the official        Microsoft website.you would want the middle option under the header "Visual Studio 2015, 2017 and 2019" which is "x64: vc_redist.x64.exe".
   After reinstalling, try restarting your machine and then restarting MongoDB. Let me know if that works or not.
   
   
2) after that u will get this error given below
   to resolve it move the sai folder or ur name folder to public folder in users in c drive.
   this will resolve the issue....
   

{"t":{"$date":"2020-09-18T17:46:41.174+05:30"},"s":"I",  "c":"CONTROL",  "id":23285,   "ctx":"main","msg":"Automatically disabling TLS 1.0, to force-enable TLS 1.0 specify --sslDisabledProtocols 'none'"}
{"t":{"$date":"2020-09-18T17:46:41.930+05:30"},"s":"W",  "c":"ASIO",     "id":22601,   "ctx":"main","msg":"No TransportLayer configured during NetworkInterface startup"}
{"t":{"$date":"2020-09-18T17:46:41.931+05:30"},"s":"I",  "c":"NETWORK",  "id":4648602, "ctx":"main","msg":"Implicit TCP FastOpen in use."}
{"t":{"$date":"2020-09-18T17:46:41.932+05:30"},"s":"I",  "c":"STORAGE",  "id":4615611, "ctx":"initandlisten","msg":"MongoDB starting","attr":{"pid":11812,"port":27017,"dbPath":"/Users/sai/mongodb-data","architecture":"64-bit","host":"DESKTOP-PSKVGKT"}}
{"t":{"$date":"2020-09-18T17:46:41.949+05:30"},"s":"I",  "c":"CONTROL",  "id":23398,   "ctx":"initandlisten","msg":"Target operating system minimum version","attr":{"targetMinOS":"Windows 7/Windows Server 2008 R2"}}
{"t":{"$date":"2020-09-18T17:46:41.950+05:30"},"s":"I",  "c":"CONTROL",  "id":23403,   "ctx":"initandlisten","msg":"Build Info","attr":{"buildInfo":{"version":"4.4.1","gitVersion":"ad91a93a5a31e175f5cbf8c69561e788bbc55ce1","modules":[],"allocator":"tcmalloc","environment":{"distmod":"windows","distarch":"x86_64","target_arch":"x86_64"}}}}
{"t":{"$date":"2020-09-18T17:46:41.951+05:30"},"s":"I",  "c":"CONTROL",  "id":51765,   "ctx":"initandlisten","msg":"Operating System","attr":{"os":{"name":"Microsoft Windows 10","version":"10.0 (build 18362)"}}}
{"t":{"$date":"2020-09-18T17:46:41.952+05:30"},"s":"I",  "c":"CONTROL",  "id":21951,   "ctx":"initandlisten","msg":"Options set by command line","attr":{"options":{"storage":{"dbPath":"/Users/sai/mongodb-data"}}}}
{"t":{"$date":"2020-09-18T17:46:41.954+05:30"},"s":"E",  "c":"STORAGE",  "id":20557,   "ctx":"initandlisten","msg":"DBException in initAndListen, terminating","attr":{"error":"IllegalOperation: Attempted to create a lock file on a read-only directory: /Users/sai/mongodb-data"}}
{"t":{"$date":"2020-09-18T17:46:41.978+05:30"},"s":"I",  "c":"REPL",     "id":4784900, "ctx":"initandlisten","msg":"Stepping down the ReplicationCoordinator for shutdown","attr":{"waitTimeMillis":10000}}
{"t":{"$date":"2020-09-18T17:46:41.978+05:30"},"s":"I",  "c":"COMMAND",  "id":4784901, "ctx":"initandlisten","msg":"Shutting down the MirrorMaestro"}
{"t":{"$date":"2020-09-18T17:46:41.979+05:30"},"s":"I",  "c":"SHARDING", "id":4784902, "ctx":"initandlisten","msg":"Shutting down the WaitForMajorityService"}
{"t":{"$date":"2020-09-18T17:46:41.980+05:30"},"s":"I",  "c":"NETWORK",  "id":20562,   "ctx":"initandlisten","msg":"Shutdown: going to close listening sockets"}
{"t":{"$date":"2020-09-18T17:46:41.980+05:30"},"s":"I",  "c":"NETWORK",  "id":4784905, "ctx":"initandlisten","msg":"Shutting down the global connection pool"}
{"t":{"$date":"2020-09-18T17:46:41.981+05:30"},"s":"I",  "c":"STORAGE",  "id":4784906, "ctx":"initandlisten","msg":"Shutting down the FlowControlTicketholder"}
{"t":{"$date":"2020-09-18T17:46:41.982+05:30"},"s":"I",  "c":"-",        "id":20520,   "ctx":"initandlisten","msg":"Stopping further Flow Control ticket acquisitions."}
{"t":{"$date":"2020-09-18T17:46:41.982+05:30"},"s":"I",  "c":"NETWORK",  "id":4784918, "ctx":"initandlisten","msg":"Shutting down the ReplicaSetMonitor"}
{"t":{"$date":"2020-09-18T17:46:41.983+05:30"},"s":"I",  "c":"SHARDING", "id":4784921, "ctx":"initandlisten","msg":"Shutting down the MigrationUtilExecutor"}
{"t":{"$date":"2020-09-18T17:46:41.984+05:30"},"s":"I",  "c":"CONTROL",  "id":4784925, "ctx":"initandlisten","msg":"Shutting down free monitoring"}
{"t":{"$date":"2020-09-18T17:46:41.985+05:30"},"s":"I",  "c":"FTDC",     "id":4784926, "ctx":"initandlisten","msg":"Shutting down full-time data 
capture"}
{"t":{"$date":"2020-09-18T17:46:41.986+05:30"},"s":"I",  "c":"STORAGE",  "id":4784927, "ctx":"initandlisten","msg":"Shutting down the HealthLog"}
{"t":{"$date":"2020-09-18T17:46:41.986+05:30"},"s":"I",  "c":"STORAGE",  "id":4784929, "ctx":"initandlisten","msg":"Acquiring the global lock for shutdown"}
{"t":{"$date":"2020-09-18T17:46:41.988+05:30"},"s":"I",  "c":"-",        "id":4784931, "ctx":"initandlisten","msg":"Dropping the scope cache for 
shutdown"}
{"t":{"$date":"2020-09-18T17:46:42.019+05:30"},"s":"I",  "c":"CONTROL",  "id":20565,   "ctx":"initandlisten","msg":"Now exiting"}
{"t":{"$date":"2020-09-18T17:46:42.020+05:30"},"s":"I",  "c":"CONTROL",  "id":23138,   "ctx":"initandlisten","msg":"Shutting down","attr":{"exitCode":100}}


###the above solution will resolve this error too

error is:: failed to conect to localhost:27017 in while working with::ROBO 3T
error pic::https://github.com/saisyama31/error-100-in-mongo-db/blob/master/error%20while%20creating%20dolder%20in%20robo%203t.jpeg





