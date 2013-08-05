# Using the CopperEggWriter Output Writer

## Deploying with the Cocktail Demo App

### 1. Save a copy of your current resources/jmxtrans.json file

```xml
    cd <path-to-embedded-jmxtrans-samples> 
    mv embedded-jmxtrans-webapp-coktail/src/main/resources/jmxtrans.json embedded-jmxtrans-webapp-coktail/src/main/resources/jmxtrans.json.original
```

### 2. Copy the CocktailDemo-specific copperegg_config.json and jmxtrans.json to resources/

```xml
    cd <path-to-embedded-jmxtrans-samples> 
    cp embedded-jmxtrans-webapp-coktail/src/main/copperegg/copperegg_configCocktailApp/*.json embedded-jmxtrans-webapp-coktail/src/main/resources/
```

### 3. Edit the (newly-copied) jmxtrans.json file

```xml
    cd <path-to-embedded-jmxtrans-samples> 
    nano embedded-jmxtrans-webapp-coktail/src/main/resources/jmxtrans.json
    In the "OutputWriters" array, find the CopperEggWriter settings.
        Replace  <YOUR_USER_NAME>  with your user name
        Replace  <YOUR_APIKEY> with your CopperEgg APIKEY
    Optionally, add any other OutputWriters to the OutputWriters array.
    Save and close jmxtrans.json
```

### 4. Build and Deploy the Cocktail Demo App as usual.


## Integrating with your Spring-enabled or Plain Java Servlet

### 1. Save a copy of your current resources/jmxtrans.json file, as in Step 1 above

### 2. Copy the copperegg_config.json and jmxtrans.json to resources/

```xml
    cp src/main/copperegg/*.json <path-to-your-resources-directory>
```
### 3. Edit the (newly-copied) jmxtrans.json file, as descibed in Step 3 above


### 4. Follow the embedded-jmxtrans instructions for building and deploying

For Spring integration:

  [embedded-jmxtrans wiki](https://github.com/jmxtrans/embedded-jmxtrans/wiki/Spring-Integration)

For Plain-Java-Servlet integration:

  [embedded-jmxtrans wiki](https://github.com/jmxtrans/embedded-jmxtrans/wiki/Plain-Java-Servlet-Integration)


For the documentation about the embedded-jmxtrans module, refer to:
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






