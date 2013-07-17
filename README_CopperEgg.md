# Embedded JmxTrans Samples with CopperEggWriter support

## Using the CopperEggWriter in the JxmTrans Cocktail Demo

To easily enable the CopperEggWriter for the Cocktail Demo, CopperEgg has provided:  
 * a custom copperegg_config.json, and   
 * a custom copperegg_jmxtrans.json.  

To run the demo, please follow these steps:

### 1.Build embedded-jmxtrans with the CopperEgg fork of embedded-jmxtrans. Hopefully this fork will be short-lived, and the CopperEggWriter will be included in upcoming releases of embedded-jmxtrans.
  
  You can clone it and build as follows:

```xml
git clone https://github.com/sjohnsoncopperegg/embedded-jmxtrans.git
cd embedded-jmxtrans
mvn install dependency:go-offline
```

### 2. Clone the CopperEgg fork of the embedded-jmxtrans-samples repo:

```xml
git clone https://github.com/sjohnsoncopperegg/embedded-jmxtrans-samples.git
```

### 3. Replace jmxtrans.json with copperegg_jmxtrans.json, then edit jmxtrans.json:

```xml
cd embedded-jmxtrans-samples/embedded-jmxtrans-webapp-coktail/src/main/resources
cp copperegg_jmxtrans.json jmxtrans.json
edit jmxtrans.json
    In the "OutputWriters" array, find the CopperEggWriter settings.
        Replace  <YOUR_USER_NAME>  with your user name
        Replace  <YOUR_APIKEY> with your CopperEgg APIKEY
Save and close jmxtrans.json
```

### 4. Optionally, edit copperegg_config.json:

This is not recommended, as this json file has been specifically created for the jmxtrans Cocktail Demo. 
This config will create 3 metric groups:
 * Sample_jvm_metrics  
 * Sample_tomcat_metrics  
 * Sample_Cocktail_App_metrics  

It will also create 3 dashboards:
 * Sample_jvm_dash  
 * Sample_tomcat_dash  
 * Sample_Cocktail_App


### 5. Build the Cocktail App Demo

```xml
cd embedded-jmxtrans-samples
mvn install dependency:go-offline
```
 

### 6. Copy your configured app into your Tomcat webapps directory: 

```xml
cp embedded-jmxtrans-webapp-coktail/target/cocktail-app-1.0.9-SNAPSHOT.war <CATALINA_HOME>/webapps/
```

If Tomcat is not already started, start it up.
You should begin seeing metrics from you jvm, tomcat and the Cocktail Demo app within a minute or so.


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

CopperEgg has provided three JSON files in this repository, which can be used to configure the CopperEggWriter. 
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






