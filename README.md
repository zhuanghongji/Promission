# Promission

Android runtime permissions in Promise


## Intro

This library refer to [RxPermissions](https://github.com/tbruyelle/RxPermissions) design idea but without RxJava.

You can use it without any other lib and the way just like Promise in ES6.


## Setup

To use this library, your `minSdkVersion` must be >= 14.

```gradle
dependencies {
    implementation project(':promission')
}
```


## Usage

```java
Promission.with(this)
    .request(Manifest.permission.CAMERA)
    .then(() -> {
        // Always call pre-M
        // I can control the camera now
    })
    .catch(() -> {
        // Oups permission denied
    })
    .finally(() -> {
        // To do finally
    });
```

**NOTE:** `Promission.with(this)` the `this` parameter can be an Activity or a Fragment. If you are using `RxPermissions` inside of a fragment you should pass the fragment instance(`new RxPermissions(this)`) as constructor parameter rather than `new RxPermissions(fragment.getActivity())` or you could face a `java.lang.IllegalStateException: FragmentManager is already executing transactions`.  


## Todo

- [ ] Just need to write down the code, haha.


# License

```
Copyright (C) 2018 zhuanghongji

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
