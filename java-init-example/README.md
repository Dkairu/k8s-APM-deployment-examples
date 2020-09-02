In this example I am not touching the Spring Java app's container. I am passing the New Relic Appname, license key and also a flag to start the APM agent with the spring app 
using Env variables i.e 

`- name: JAVA_TOOL_OPTIONS
 value: "-javaagent:/home/gradle/project/newrelic/newrelic.jar"`

The sleep.sh is a small script to copy the downloaded java agent contents from the container downloading the Java agent to a shared mounted volume /usr/local/newrelic/

You can use any directory in the app container where the New Relic agents will copied to, in this example I used /home/gradle/project/newrelic/ which will be created and mounted.

After you run the yaml you should see your app in NewRelic UI 

![Init App](https://github.com/Dkairu/k8s-APM-deployment-examples/blob/master/java-init-example/screenshots/image1.png)
