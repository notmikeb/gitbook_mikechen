#dot 

## dot editor 
http://vincenthee.github.io/DotEditor/

## reference
參考資料
https://www.graphviz.org

http://www.graphviz.org/pdf/dotguide.pdf


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

format
```
 <class-name> | <fields> | <methods>
```
a real case - code snippet
```
        Animal [
                label = "{Animal|+ name : string\l+ age : int\l|+ die() : void\l}"
        ]
```

![dot_animalclass](/assets/dot_animalclass.png)


###  Animal, dot, cat 3 classes

a real case with whole script content
```
digraph G {
    fontname="Bitstream Vera Sans";
    fontsize=8;
    edge [fontname="Bitstream Vera Sans", 
          fontsize=8];
    node [fontname="Bitstream Vera Sans", 
          fontsize=8, 
          shape="record"];
    Animal [label="{Animal|+ name : string\l+ age : int\l|+ die() : void\l}"];
    Dog [label="{Dog||+ bark() : void\l}"];
    Cat [label="{Cat||+ meow() : void\l}"];
    Dog -> Animal;
    Cat -> Animal;
    edge [headlabel="0..*", 
          arrowhead="none", 
          taillabel="0..*"];
    Dog -> Cat;
}
```
![dot_animal](/assets/dot_animal_dog_cat.png)
### dot sequence diagram


### dot structure
use html 
```
digraph html {
    edge [comment="Wildcard node added automatic in EG."];
    node [comment="Wildcard node added automatic in EG."];
    abc [shape=none, 
         margin=0, 
         label=<
                 <TABLE BORDER="0" CELLBORDER="1" CELLSPACING="0" CELLPADDING="4">
                 <TR><TD ROWSPAN="3"><FONT COLOR="red">hello</FONT><BR/>world</TD>
                 <TD COLSPAN="3">b</TD>
                 <TD ROWSPAN="3" BGCOLOR="lightgrey">g</TD>
                 <TD ROWSPAN="3">h</TD>
                </TR>
                <TR><TD>c</TD>
                 <TD PORT="here">d</TD>
                 <TD>e</TD>
                 </TR>
                 <TR><TD COLSPAN="3">f</TD>
                 </TR>
                 </TABLE>>];
}

```



