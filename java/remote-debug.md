# Expose JMX for remote debugging of tomcat

Sometimes can be useful to check the status of our remote tomcat server.
One way of doing this is to use remote management and `jvisualvm`.

To enable remote management you need to add these options to your 
`catalina.sh` command of you remote tomcat

```
#expose JMX for remote debug
JAVA_OPTS="$JAVA_OPTS -Dcom.sun.management.jmxremote"
JAVA_OPTS="$JAVA_OPTS -Dcom.sun.management.jmxremote.port=<your-post>"
JAVA_OPTS="$JAVA_OPTS -Dcom.sun.management.jmxremote.authenticate=false"
JAVA_OPTS="$JAVA_OPTS -Dcom.sun.management.jmxremote.ssl=false"
```

Once you've done this, you can run `jvisualvm` to monitor your tomcat remotely.
In jvisualvm you should:
1. Add a new remote host;
2. Enter the coordinates for the host (url) 
3. Add a JMX connection, using the port you provided in the configuration

Now you can monitor your tomcat!