# Sphinx alpine

Info :

*   [RST syntax](http://docutils.sourceforge.net/rst.html)
*   [shinx](http://www.sphinx-doc.org/en/stable/)

Require :

*   [Docker](https://www.docker.com)

## How to start

Generate base project
```
docker run -it -v ${PWD}/example/mydocs:/root/docs cl3m3nt/sphinx
```

Answer the questions...
```
> Root path for the documentation [.]:
> Separate source and build directories (y/n) [n]: y
> Name prefix for templates and static dir [_]:
> Project name: Test_project
> Author name(s): Cl3m3nt
> Project version: 0.1
> Project release [0.1]:
> Project language [en]:

....
```

My project base sphinx
```
user@computer - ~/example/mydocs > tree
├── Makefile
├── build
├── make.bat
└── source
    ├── _static
    ├── _templates
    ├── conf.py
    └── index.rst

4 directories, 4 files
```

## Make docs

Add file `.rest` to source
```
example/mydocs/source
├── _static
├── _templates
├── conf.py
├── index.rst
└── test.rst
```

Exemple for html..
```
user@computer - ~/example/mydocs > docker run -it -v ${PWD}/example/mydocs:/root/docs cl3m3nt/sphinx make html
Running Sphinx v1.5.5
loading pickled environment... done
building [mo]: targets for 0 po files that are out of date
building [html]: targets for 1 source files that are out of date
updating environment: 0 added, 1 changed, 0 removed
reading sources... [100%] test
looking for now-outdated files... none found
pickling environment... done
checking consistency... done
preparing documents... done
writing output... [100%] test
generating indices... genindex
writing additional pages... search
copying static files... done
copying extra files... done
dumping search index in English (code: en) ... done
dumping object inventory... done
build succeeded.

Build finished. The HTML pages are in build/html.
```


### Other build

| Type | Description |
| :-------: |:------|
|  html         | to make standalone HTML files |
|  dirhtml      | to make HTML files named index.html in directories |
|  singlehtml   | to make a single large HTML file |
|  pickle       | to make pickle files |
|  json         | to make JSON files |
|  htmlhelp     | to make HTML files and an HTML help project |
|  qthelp       | to make HTML files and a qthelp project |
|  devhelp      | to make HTML files and a Devhelp project |
|  epub         | to make an epub |
|  latex        | to make LaTeX files, you can set PAPER=a4 or PAPER=letter |
|  latexpdf     | to make LaTeX and PDF files (default pdflatex) |
|  latexpdfja   | to make LaTeX files and run them through platex/dvipdfmx |
|  text         | to make text files |
|  man          | to make manual pages |
|  texinfo      | to make Texinfo files |
|  info         | to make Texinfo files and run them through makeinfo |
|  gettext      | to make PO message catalogs |
|  changes      | to make an overview of all changed/added/deprecated items |
|  xml          | to make Docutils-native XML files |
|  pseudoxml    | to make pseudoxml-XML files for display purposes |
|  linkcheck    | to check all external links for integrity |
|  doctest      | to run all doctests embedded in the documentation (if enabled) |
|  coverage     | to run coverage check of the documentation (if enabled) |


# Env variables

## Sphinx-quickstart default value

| Name | default value | Description |
| :-------: |:------|:------|
| _SPHINX_DEFAULT_THEME | alabaster | default theme |

## Rewrite Sphinx-quickstart default value

| Name | default value | Description |
| :-------: |:------|:------|
| SPHINX_DEFAULT_THEME | sphinx_rtd_theme | default theme |
