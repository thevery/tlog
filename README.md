Quickstart (not yet implemented)
======
 - Add dependency and plugin (more details about intergration)
 - Annotate with `@XXX` or invoke static `TLog.d(...)` (more about annotations and calls)
 - Enable with gradle, resources or static (`TLog.enableFile(true/false)`) (more about configuration here)
 - Check logcat or file (`/data/Android/com.packagename/file.log`)

tlog
======
Simple yet powerful java/android logger with following features:
 - Compile-time configuration
 - Logging to file(s) and logcat
 - Static log methods with automatic tags
 - TBD
 - Special pluggable loggers for Roboelectric etc

TODO
=======
 - Support Android TrafficStats socket tagging.
 - Add some docs
 - Logget.in() and Logger.out()
 - Add runtime configuration
 - Improve output format for logging to file
 - Compile-time annotations
 - Improve multiline/long logs
 - Variables auto-dump: `TLog.d(x,y,z)` => `class.method: x = 'x', y = 'y', z = 'z'`

Add logger to project
=======

```groovy
repositories {
    maven {
        url ''
    }
}

dependencies {
    compile ''
}
```

Runtime logger usage
=======
 - TLog.v(), TLog.i(), TLog.d() - printed only in debug mode
 - TLog.w() and TLog.e() always printed
 - TLog.d("Hello") will produce ClassName.methodName/D: Hello in log
 - TLog.in(Object... args) and TLog.out(Object result) will produce D/ClassName.methodName>>(first="Hello", last="World") and D/ClassName.methodName<<[8ms] = "Hello World"

