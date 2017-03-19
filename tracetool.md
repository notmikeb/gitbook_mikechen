# TraceTool

What is TraceTool
* A viewer (written in unmanaged Delphi) that displays multiple kinds of sources (from the provided framework, log file, event log, or the OutputDebugString method).
* An easy and powerful client framework to send simple traces, grouped traces, class and object viewer, dump, and call stack.

https://www.codeproject.com/articles/5498/tracetool-the-swiss-army-knife-of-trace

![](/assets/server1.jpg)

![](/assets/overview.jpg)

### python sample

```

import logging
import logging.config
from tracetool import *  #IGNORE:W0401
from tracetool import _Internals

class CustomTraceLogger(logging.StreamHandler):
    def __init__(self):
	    logging.StreamHandler.__init__(self)

    def emit(self, record):
		msg = self.format(record)
		print record
		if record.levelname == "ERROR":
			TTrace.error.send(msg)
		elif record.levelname == "INFO":
			TTrace.debug.send(msg)
		elif record.levelname == "WARNING":
			TTrace.warning.send(msg)
		else:
			TTrace.debug.send(msg)
		self.flush()



logging.getLogger().setLevel(logging.DEBUG)
logging.getLogger().addHandler(CustomTraceLogger())
logging.debug('This message should go to the log file')
logging.info('So should this')
logging.warning('And this, too')
logging.error("this is a error msg")
```

### c# library TraceTool.dll
![](/assets/2017-03-19 21_38_12-Vs8 Windows TraceTool Dot net Library and Demos - Microsoft Visual Studio.png)
Need to use gacutil to register the TraceTool.dll

"$(DevEnvDir)..\..\SDK\v2.0\bin\gacutil" -i $(TargetFileName)

Here has some QnA
http://stackoverflow.com/questions/11854308/why-am-i-getting-error-cs0246-the-type-or-namespace-name-could-not-be-found

### c# sample
```
using System;
using TraceTool ;

class trace1
{
public static void Main(string[] args)
{
TTrace.Debug.Send("Hello").Send("World");
Console.WriteLine("hello, world");
TTrace.Flush();
}
}
```

### compile sample
```
J:\temp>csc trace1.cs /r:TraceTool.dll
Microsoft (R) Visual C# Compiler version 1.0.0.50618
Copyright (C) Microsoft Corporation. All rights reserved.

J:\temp>trace1
hello trace
```
![](/assets/2017-03-19 21_45_04-Trace and Object inspector Tool.png)

