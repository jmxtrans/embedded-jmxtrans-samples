# CopperEgg-jmxmon

  copperegg-jmxmon is a tool for monitoring your Tomcat servers and the JVMs upon which they run. 
A very small, minimal webapp is created that will run on your Tomcat server. From there, copperegg-jmxmon wil push collect JVM and Tomcat metrics using JMX, and puysh the results to CopperEgg.
copperegg-jmxmon is built upon the open source embedded-jmxtrans code.

  This monitor does not need to be compiled with your Tomcat app. 

# Setting up copperegg-jmxmon

### 1.Build embedded-jmxtrans with the CopperEgg fork of embedded-jmxtrans. Hopefully this fork will be short-lived, and the CopperEggWriter will be included in upcoming releases of embedded-jmxtrans.
  
  You can clone and build it as follows:

```xml
git clone https://github.com/CopperEgg/embedded-jmxtrans.git
cd embedded-jmxtrans
mvn install dependency:go-offline
```

### 2. Clone the CopperEgg fork of the embedded-jmxtrans-samples repo:

```xml
git clone https://github.com/CopperEgg/embedded-jmxtrans-samples.git
```

### 3. Add your Username and CopperEgg APIKey to jmxtrans.json

```xml
cd embedded-jmxtrans-samples/copperegg-jmxmon/src/main/resources
edit jmxtrans.json
    In the "OutputWriters" array, find the CopperEggWriter settings.
        Replace  <YOUR_USER_NAME>  with your user name
        Replace  <YOUR_APIKEY> with your CopperEgg APIKEY
Save and close jmxtrans.json
```

### 4. Optionally, edit copperegg_config.json:

This is only recommended if you are familiar with the CopperEgg API. 
This config will create a number of metric groups, designed for optimal efficiency when running with embedded-jmxtrans.

It will also create 2 dashboards:
 * jvm_dashboard  
 * tomcat_dashboard  

### 5. Build copperegg-jmxmon 

```xml
cd embedded-jmxtrans-samples/copperegg-jmxmon
mvn install dependency:go-offline
```

### 6. Copy copperegg-jmxmon to your Tomcat webapps directory 

```xml
cp embedded-jmxtrans-samples/copperegg-jmxmon/target/embedded-jmxmon-1.0-SNAPSHOT.war $CATALINA_HOME/webapps/
```

If Tomcat is not already started, start it up.
You should begin seeing metrics from your tomcat servers and jvms within a minute or so.


For documentation about the embedded-jmxtrans module, refer to:
* [Documentation](https://github.com/jmxtrans/embedded-jmxtrans/wiki)
* [Latest javadocs](http://jmxtrans.github.com/embedded-jmxtrans/apidocs/)

To learn more about CopperEgg, and to sign up for a free trial: 
* [CopperEgg Homepage](http://www.copperegg.com)
* [CopperEgg Signup](https://app.copperegg.com/signup)
* [CopperEgg Login](https://app.copperegg.com/login)


License
==================

Please refer to the LICENSE and NOTIFICATION files included by the authors of embedded-jmxtrans and embedded-jmxtrans-samples.

CopperEgg has provided two JSON files in this repository, which can be used to configure the CopperEggWriter. 
These files are made available under the terms of the MIT License:

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, including without
limitation the rights to use, copy, modify, merge, publish, distribute,
sublicense, and/or sell copies of the Software, and to permit persons
to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT. IN NO EVENT SHALL
THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

