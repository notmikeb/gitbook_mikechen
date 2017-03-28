### python xml to object

http://stackoverflow.com/questions/418497/how-to-convert-xml-to-objects

```
>>> xml = """<main>
... <object1 attr="name">content</object1>
... <object1 attr="foo">contenbar</object1>
... <test>me</test>
... </main>"""
>>> from lxml import objectify
>>> main = objectify.fromstring(xml)
>>> main.object1[0]
'content'
>>> main.object1[1]
'contenbar'
>>> main.object1[0].get("attr")
'name'
>>> main.test
'me'
```

### csharp serialize object to xml
http://stackoverflow.com/questions/4123590/serialize-an-object-to-xml
