To reproduce:

```shell
$  ./mvnw org.openrewrite.maven:rewrite-maven-plugin:4.37.0:run
```

which results in
```
---------------------------------------------------
Exception in thread "main" java.lang.reflect.InvocationTargetException
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.base/java.lang.reflect.Method.invoke(Method.java:566)
	at org.apache.maven.wrapper.BootstrapMainStarter.start(BootstrapMainStarter.java:53)
	at org.apache.maven.wrapper.WrapperExecutor.execute(WrapperExecutor.java:152)
	at org.apache.maven.wrapper.MavenWrapperMain.main(MavenWrapperMain.java:76)
Caused by: java.lang.StackOverflowError
	at java.base/sun.nio.cs.UTF_8.updatePositions(UTF_8.java:79)
	at java.base/sun.nio.cs.UTF_8$Encoder.encodeArrayLoop(UTF_8.java:509)
	at java.base/sun.nio.cs.UTF_8$Encoder.encodeLoop(UTF_8.java:564)
	at java.base/java.nio.charset.CharsetEncoder.encode(CharsetEncoder.java:576)
	at java.base/sun.nio.fs.UnixPath.encode(UnixPath.java:136)
	at java.base/sun.nio.fs.UnixPath.<init>(UnixPath.java:69)
	at java.base/sun.nio.fs.UnixFileSystem.getPath(UnixFileSystem.java:279)
	at java.base/java.nio.file.Path.resolve(Path.java:515)
	at org.openrewrite.maven.internal.MavenPomDownloader.getParentWithinProject(MavenPomDownloader.java:180)
	at org.openrewrite.maven.internal.MavenPomDownloader.getAncestryWithinProject(MavenPomDownloader.java:161)
	at org.openrewrite.maven.internal.MavenPomDownloader.getAncestryWithinProject(MavenPomDownloader.java:165)
	at org.openrewrite.maven.internal.MavenPomDownloader.getAncestryWithinProject(MavenPomDownloader.java:165)
```

