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

format
```
 <class-name> | <fields> | <methods>
```
a real case
```
        Animal [
                label = "{Animal|+ name : string\l+ age : int\l|+ die() : void\l}"
        ]
```

![dot_animalclass](/assets/dot_animalclass.png)


###  Animal, dot, cat 3 classes

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