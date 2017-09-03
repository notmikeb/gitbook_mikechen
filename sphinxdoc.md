
# autodoc from python source code with sphinx

## install sphinx
dos>python -m pip install sphinx

## .rst tutorial
http://www.cnblogs.com/zzqcn/p/5096876.html
\`\`code\`\`
each paragraph uses blank line as separator
official tutorial of .rst 
http://docutils.sourceforge.net/rst.html
online test sample
http://rst.ninjs.org/
 
## read-the-doc website
https://read-the-docs.readthedocs.io/en/latest/getting_started.html#in-markdown 

## Use sphinx to generate html
```
project_workspace
    project_name
        __init__.py
        source_file_1.py
        source_file_2.py
    docs
    run.py
```

separate the source of sphinx and build directories of sphinx: Y
```
project_workspace
    project_name
        __init__.py
        source_file_1.py
        source_file_2.py
    docs
        source
            conf.py
            index.rst
        build
            html
                index.html
            doctree
                index.doctree
    run.py
```

under docs folder

sphinx_quickstart.exe
```
enable autodoc: Y
separate the source of sphinx and build directories of sphinx: Y
```

### Edit conf.py to include the right path and enable autodoc extension

http://www.patricksoftwareblog.com/python-documentation-using-sphinx/
enable to include source code folder
Uncomment the following line from ‘…/docs/source/conf.py’ and make it point to the top-level directory in your project:
```
import sys
import os
sys.path.insert(0, os.path.abspath('../..'))
```

get an err
ERROR: Unknown directive type "autoclass"
check the conf.py
```
extensions = ['sphinx.ext.autodoc']
```

### autodoc - create *.rst from *.py

under
sphinx-apidoc -f -o source/ ../python-module-path
```
J:\git_home\git1\doc>c:\python27\Scripts\sphinx-apidoc.exe -f -o source ..\mymodule1
Creating file source\mymodule1.rst.
Creating file source\mymodule1.b.rst.
Creating file source\modules.rst.
```

### make output

> make html

Open the index.html

### change theme

install the rtd theme and change theme to sphinx_rtd_theme in config.py

```
python -m pip install sphinx_rtd_theme
```
tutorial:
https://pypi.python.org/pypi/sphinx_rtd_theme

In your conf.py file:

```
import sphinx_rtd_theme
html_theme = "sphinx_rtd_theme"
html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]


load ui projects. has error
use 'if __name__ == "__main__"' to avoid import to autodoc
```

## Markdown in sphinx

add .md to sphinx 
install recommonmark
```
python -m pip install commonmark recommonmark
```
modify conf.py
```
from recommonmark.parser import CommonMarkParser

source_parsers = {
    '.md': CommonMarkParser,
}

source_suffix = ['.rst', '.md']
```
discuss article
https://stackoverflow.com/questions/2471804/using-sphinx-with-markdown-instead-of-rst
```


## sphinx extensions
More support markup
https://bitbucket.org/birkenfeld/sphinx-contrib

## .md and .rst comparsion
discuss
https://www.zhihu.com/question/19851600
sample comparsion
http://www.worldhello.net/gotgithub/appendix/markups.html