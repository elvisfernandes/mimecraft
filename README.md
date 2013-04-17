Mime Writer
===========

Utility for creating RFC-compliant multipart and form-encoded HTTP request bodies.



Download
--------

Downloadable .jars can be found on the [GitHub download page][2].

You can also depend on the .jar through Maven:

```xml
<dependency>
  <groupId>com.squareup.mimewriter</groupId>
  <artifactId>mimewriter<artifactId>
  <version>(insert latest version)</version>
</dependency>
```



Examples
--------

Form-encoded content:
```java
FormEncoding fe = new FormEncoding.Builder()
    .addPart("name", "Lorem Ipsum")
    .addPart("occupation", "Filler Text")
    .build();
```

Multipart content:
```java
Multipart m = new Multipart.Builder("123")
    .addPart(new Part.Builder()
        .contentType("image/png")
        .body(new File("/foo/bar/baz.png"))
        .build())
    .addPart(new Part.Builder()
        .contentType("text/plain")
        .body("The quick brown fox jumps over the lazy dog.")
        .build())
    .build();
```



License
=======

    Copyright 2013 Square, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


 [1]: http://repository.sonatype.org/service/local/artifact/maven/redirect?r=central-proxy&g=com.squareup.mimewriter&a=mimewriter&v=LATEST