# Jython Vert.x API Implementation Module

This project builds a Vert.x module which implements Python Vert.x API support using Jython.

All Vert.x language support is implemented in the form of modules which are (potentially) loaded on demand by Vert.x when needed.

## UPDATED:

This version of module provides supporting of Jython 2.7beta1.
It "just works" and has no deep testing. If some errors occurs - feel
free to create a related issue.

### Installing

I makes this as follows:

```bash
$ git clone https://github.com/rdolgushin/mod-lang-jython
$ cd mod-lang-jython
$ ./gradlew assemble
```

Then this:

```bash
$ cp build/io.vertx~lang-jython~2.1.0-CUSTOM-PYTHON-2.7 $VERTX_PATH/sys-mods/
$ # + edit $VERTX_PATH/conf/langs.properties
```

or this:

```bash
$ cp build/io.vertx~lang-jython~2.1.0-CUSTOM-PYTHON-2.7 $MY_PROJECT/build/mods/
$ # + edit $MY_PROJECT/src/main/resources/langs.properties
```

In each cases `langs.properties` looks like following:


```jproperties

# Something above...

jython=io.vertx~lang-jython~2.1.0-CUSTOM-PYTHON-2.7:org.vertx.java.platform.impl.JythonVerticleFactory

# Something here...

.py=jython

# Something below...

```

Nice! Now we`re ready for testing:

```python
# test.py
import sys

print sys.version

# --> # 2.7b1 (default:ac42d59644e9, Feb 9 2013, 15:24:52) 
#     [OpenJDK Server VM (Oracle Corporation)]
```

It works!
