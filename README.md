# Java binding as Maven artifact for Capstone disassembly framework

This is a fork of the excellent original [Capstone disassembly framework](https://github.com/aquynh/capstone). The only difference is that the Java binding library was transformed into a Maven project. The resulting Maven artifact is available via the usual Maven repository.

## Release notes
### 3.0.5-rc2

* This is the initial compatible Java binding version distributed as Maven artifact

## Roadmap

There are no plans for further modifications on this fork (except the conversion of the Java binding code into a Maven project). Every time when the original Capstone project ([aquynh/capstone](https://github.com/aquynh/capstone)) provides a new release then this code (inclusive Java binding) will be forked again, modified for Maven and distributed as Maven artifact for public use.

## Issue tracking

Bugs, feature requests or pull requests should be reported via Github's issue tracking system. We only accept requests that concern the conversion to Maven project of the Java binding part. Issues in Capstone itself or in the Java binding code should be reported at the [original project site](https://github.com/aquynh/capstone/issues).

## Contributions

If you would like to help us please contact us via issue tracking or email.

## License & Author

The license and author is the same as in the original project. We ([TRANScurity](http://transcurity.co/)) only modify the structure of Java binding code in order to make it compatible with Maven.

# Developer Guide
## Getting started

You can import the artifact by:

```xml
<dependency>
    <groupId>com.github.transcurity</groupId>
    <artifactId>capstone</artifactId>
    <version>W.X.Y-rcZ</version>
</dependency>
```

Furthermore, you need to obtain the native binaries from <http://www.capstone-engine.org/> or from the releases page: <https://github.com/aquynh/capstone/releases>

Please note that the provided command line based test classes from the original project of Java binding are not intact anymore, because the binding code classes were moved in order to create a Maven compatible structure.






https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
