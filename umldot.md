#dot 
## dot tutorial
http://www.ffnn.nl/pages/articles/media/uml-diagrams-using-graphviz-dot.php

```
digraph G {
        fontname = "Bitstream Vera Sans"
        fontsize = 8

        node [
                fontname = "Bitstream Vera Sans"
                fontsize = 8
                shape = "record"
        ]

        edge [
                fontname = "Bitstream Vera Sans"
                fontsize = 8
        ]
      
```   

### a animal class

```
 <class-name> | <fields> | <methods>
```

```
        Animal [
                label = "{Animal|+ name : string\l+ age : int\l|+ die() : void\l}"
        ]
```
          