# TraceTool


### python sample

### c# sample
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

### compile sample


J:\temp>csc trace1.cs /r:TraceTool.dll
Microsoft (R) Visual C# Compiler version 1.0.0.50618
Copyright (C) Microsoft Corporation. All rights reserved.

J:\temp>trace1
hello trace