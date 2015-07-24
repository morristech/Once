# Once
A small Android library to manage one-off operations.

----

Some things should happen once.
* Users should only get the guided tour _once_. 
* Release notes should only pop up _once every app upgrade_. 
* Your app should only phone home to update content _once every hour_.

`Once` provides a simple API to track whether or not your app has already performed an action within a given scope.

## Usage

First things first, you'll need to initialise Once on start up. In your `Application` class's `onCreate()` override add the follow:

```java
Once.initialise(this);
```

Now you're ready to go. Say you wanted to navigate to a 'WhatsNew' Activity every time your app is upgraded:

```java
String whatsNew = "WhatsNew";

if (!Once.beenDone(Once.THIS_APP_VERSION, whatsNew)) {
    startActivity(this, WhatsNewActivity.class);
    Once.markDone(whatsNew);
}
```

## Installation


## License

```
Copyright 2015 Jon Finerty

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```