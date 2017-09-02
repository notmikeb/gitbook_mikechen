
# autodoc from python source code with sphinx

## install sphinx
dos>python -m pip install sphinx

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


## change theme
install the rtd theme and change theme to sphinx_rtd_theme in config.py
```
python -m pip install sphinx_rtd_theme
```
https://pypi.python.org/pypi/sphinx_rtd_theme
