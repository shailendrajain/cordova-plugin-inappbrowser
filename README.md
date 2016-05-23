---
title: Inappbrowser (Supports Bad SSL)
description: Open an in-app browser window. 
This version of InAppBrowser can configured to ByPass all certificates errors. 
THis is frequently required during testing with 
Test environment / Stage / Prepod environment which has self signed or broken certificates.

---
<!--
# license: Licensed to the Apache Software Foundation (ASF) under one
#         or more contributor license agreements.  See the NOTICE file
#         distributed with this work for additional information
#         regarding copyright ownership.  The ASF licenses this file
#         to you under the Apache License, Version 2.0 (the
#         "License"); you may not use this file except in compliance
#         with the License.  You may obtain a copy of the License at
#
#           http://www.apache.org/licenses/LICENSE-2.0
#
#         Unless required by applicable law or agreed to in writing,
#         software distributed under the License is distributed on an
#         "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
#         KIND, either express or implied.  See the License for the
#         specific language governing permissions and limitations
#         under the License.
-->

[![Build Status](https://github.com/shailendrajain/cordova-plugin-inappbrowser.svg?branch=master)](https://github.com/shailendrajain/cordova-plugin-inappbrowser)

# cordova-plugin-inappbrowser (By Pass SSL Errors)

Refer the Original document of cordova-plugin-inappbrowser. Behaviour of this plugin is similar to original plugin.
For now feature of bypassing SSL error is available only on Android Platform. 

#Instruction to integrate the Plugin from local path 

Step 1 : Remove already integrated version with following command 
cordova plugin remove cordova-plugin-inappbrowser

Step 2 :  Adding plugin from local folder which  having plugin.xml file 
cordova plugin add <Path on your system >\inappbrowser 

Usage in JS code : 
//Allow URLs with BAD SSL 
  var ref = cordova.InAppBrowser.open('https://self-signed.badssl.com/', '_black', 'location=yes,badssl=true');
var ref = cordova.InAppBrowser.open('https://self-signed.badssl.com/', '_black', 'location=yes,badssl=yes');

//Block URLs with BAD SSL
var ref = cordova.InAppBrowser.open('https://self-signed.badssl.com/', '_black', 'location=yes,badssl=no');
var ref = cordova.InAppBrowser.open('https://self-signed.badssl.com/', '_black', 'location=yes,badssl=false');
var ref = cordova.InAppBrowser.open('https://self-signed.badssl.com/', '_black', 'location=yes');

WARNING : Intented for only Dev environment. Use the plugin in Production environment on your risk.
It leaves your users suseptible for Man-in-the-middle attack
