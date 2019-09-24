# Kill the process


### had the problem that running 3 same process
- Error: listen EADDRINUSE :::8080


##### strategy
```unix
<!-- install the lsof -->
  sudo apt-get install lsof
  lsof
  <!-- check the process id with 8080 -->
  lsof -i tcp:8080
  <!-- when running the process, node number may change (actully it kept changing)
  and the PID number wont -->
  kill -9 21243
```