# Archive Utilities for Eclipse
The Archive Utilities extend the Eclipse IDE to view the structure and content and extract zip archive files within the workspace. Zip-compatible archives like JARs, WARs, etc. are of course also supported.

This document is targeted at developers. For user documentation, pease read [this document](http://rherrmann.github.com/com.codeaffine.archive/index.html)

## Repository Contents

### Code 
The bundles `com.codeaffine.archive.contenttype` and `com.codeaffine.archive.ui` contain all the functionality.

### Tests
Each working code bundle has an accomanying fragment (with the suffix `.test`) that contains JUnit tests.
In addition, there are integration tests, located in the `com.codeaffine.archive.ui.itest` bundle. These depend on [SWTBot](http://eclipse.org/swtbot) and are also run as unit tests with JUnit.
Common helper and fixture code for all tests is in `com.codeaffine.archive.testfixture`.

The `com.codeaffine.archive.alltest` bundle contains a test suite that references all unit tests (not the integration tests) and should be used to run all tests from within the IDE.

### Target Platform
The `target` project contains a [target platform](http://help.eclipse.org/indigo/index.jsp?topic=%2Forg.eclipse.pde.doc.user%2Fconcepts%2Ftarget.htm) definition that should be used for development. 

### Build
The `com.codeaffine.archive.releng` project contains everything that is necessary to build the software. The build is based on [Eclipse Tycho (version 0.14)](http://www.eclipse.org/tycho). To run the build

    cd <git-repo>/com.codeaffine.archive.releng
    mvn clean install -P <eclipse-platform>
    
&lt;eclipse-platform&gt; can be one of `eclipse-3.6`, `eclipse-3.7`, `eclipse-3.8`, `eclipse-4.2`. If you omit the -P (maven profile) command line argument, the default `eclipse-3.7` is taken.

## License
Please see the [user documentation](http://rherrmann.github.com/com.codeaffine.archive/index.html).