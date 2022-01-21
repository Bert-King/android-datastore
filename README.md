# DataStore codelab

Supporting code for [Preferences DataStore codelab](https://codelabs.developers.google.com/codelabs/android-preferences-datastore/#0) and [Proto DataStore codelab](https://codelabs.developers.google.com/codelabs/android-proto-datastore/#0).

DataStore is a new and improved data storage solution aimed at replacing SharedPreferences. Built on Kotlin coroutines and Flow, DataStore provides two different implementations: Proto DataStore, that lets you store typed objects (backed by protocol buffers) and Preferences DataStore, that stores key-value pairs. Data is stored asynchronously, consistently, and transactionally, overcoming some of the drawbacks of SharedPreferences.

关于限制数据库的行数:[详情](https://stackoverflow.com/questions/46193356/limit-the-number-of-rows-in-a-room-database)
```java
 /**
     * 参考自:https://stackoverflow.com/questions/46193356/limit-the-number-of-rows-in-a-room-database
     */
    @Transaction
    @Query("DELETE FROM posts WHERE draftId IN (SELECT draftId FROM posts ORDER BY update_time DESC LIMIT 1 OFFSET :maxColumns)")
    fun removeOldPost(maxColumns:Int)
```


License
--------
```
Copyright 2020 The Android Open Source Project

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements. See the NOTICE file distributed with this work for
additional information regarding copyright ownership. The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
