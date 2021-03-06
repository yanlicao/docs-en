---
license: licensed to the apache software foundation (asf) under one
         or more contributor license agreements.  see the notice file
         distributed with this work for additional information
         regarding copyright ownership.  the asf licenses this file
         to you under the apache license, version 2.0 (the
         "license"); you may not use this file except in compliance
         with the license.  you may obtain a copy of the license at

           http://www.apache.org/licenses/license-2.0

         unless required by applicable law or agreed to in writing,
         software distributed under the license is distributed on an
         "as is" basis, without warranties or conditions of any
         kind, either express or implied.  see the license for the
         specific language governing permissions and limitations
         under the license.

---

# The Basics

Apps built using PhoneGap Build can be set up either through our
web interface, or by using a `config.xml`.

The `config.xml` file, as specified in the [W3C widget specification](http://www.w3.org/TR/widgets/)
, allows developers to easily specify metadata about their applications. You can see a
sample `config.xml` with our
[PhoneGap Start](https://github.com/phonegap/phonegap-start/blob/master/www/config.xml) application.

<i class="glyphicon glyphicon-check"></i> Please ensure that your `config.xml` file is at the top
level of your application (the same level as your `index.html` file).
Otherwise it will not be loaded correctly.

We're continually adding features to cour `config.xml` support, to give
PhoneGap Build developers more power to customize their apps. If there are
any specific features you'd like to see support for,
[please let us know](http://getsatisfaction.com/nitobi/products/nitobi_phonegap_build).

## Essential Properties

  <table class="table">
    <tr>
      <td>
        `<widget>`
      </td>
      <td>
        <p>
          The widget element must be the root of your XML document - it lets us
          know that you are following the W3C specification. When using PhoneGap
          Build, ensure you have the following attributes set on your widget
          element
        </p>
        <p>
          `id`: the unique identifier for your application. To support all
          supported platforms, this *must* be reverse-domain name style
          (e.g. `com.yourcompany.yourapp`)
        </p>
        <p>
          `version`: for best results, use a major/minor/patch style version,
          with three numbers, such as `0.0.1`
        </p>
        <p>
          `versionCode`: (optional) when building for Android, you can set the
          versionCode by specifying it in your *config.xml*. For more information
          on Android's versionCode attribute, see
          [the Android documentation](http://developer.android.com/guide/publishing/versioning.html). 
        </p>
      </td>
    </tr>
    <tr>
      <td>`<name>`</td>
      <td>
        <p>The name of the application.</p>
        <p>
          BlackBerry only supports latin characters in the `<name>`
          attribute.
        </p>
      </td>
    </tr>
    <tr>
      <td>`<description>`</td>
      <td>
        <p>A description for your application.</p>
        <p>
          BlackBerry should keep the `<description>` element at a reasonable
          length
        </p>
      </td>
    </tr>
  </table>

### Example Config.xml
    
    <?xml version="1.0" encoding="UTF-8" ?>
        <widget xmlns   = "http://www.w3.org/ns/widgets"
            xmlns:gap   = "http://phonegap.com/ns/1.0"
            id          = "com.phonegap.example"
            versionCode = "10" 
            version     = "1.0.0" >
        
        <!-- versionCode is optional and Android only -->

        <name>PhoneGap Example</name>

        <description>
            An example for phonegap build docs. 
        </description>

        <author href="https://build.phonegap.com" email="support@phonegap.com">
            Hardeep Shoker 
        </author>

    </widget>

<a name="platform"></a>
## Platform Build Selection

By default PhoneGap Build builds your application for every platform. If you
only want to build for certain platforms you can specify these platforms with
the `gap:platform` tag.  

  <table class="table">
    <tr>
      <td>`<gap:platform>`</td>
      <td>
        <p>
        You can have zero or more of these elements present in your
        `config.xml`. If you specify none, all platforms will be built.
        </p>
        <p>
        `name`: platform to build - one of `android, ios, winphone,
        blackberry, webos, symbian`
        </p>
      </td>
    </tr>
  </table>

### Example Usage
    
    <gap:platform name="ios" />
    <gap:platform name="android" />
    <gap:platform name="webos" />
    <gap:platform name="symbian" />
    <gap:platform name="blackberry" />
    <gap:platform name="winphone" />

