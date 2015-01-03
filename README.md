j2
==

jinja2 command line client

Dependencies
------------
* [Python 2](http://python.org/) (required)
* [jinja2](http://jinja.pocoo.org/docs/dev/) (required)
* [Pyyaml](http://pyyaml.org/) (optional)

Usage
-----

```
$ j2 -h
j2 [-e | -j vars.json | -y vars.yml]
    -e render from environment
    -j render from json file
    -y render from yaml file

  read a jinja2 template from stdin and values from
  either environment or json or yaml
  (c) 2015 Sascha Spreitzer, MIT License
```

Render from environment
-----------------------
```
sspreitzer@s900x3c:~/git/j2⟫ cat test.j2 
{{ USER }}
sspreitzer@s900x3c:~/git/j2⟫ ./j2 -e < test.j2 
sspreitzer
```

Render from json
----------------
```
sspreitzer@s900x3c:~/git/j2⟫ cat test.json 
{ "USER": "json-user" }
sspreitzer@s900x3c:~/git/j2⟫ ./j2 -j test.json < test.j2
json-user
```

Render from yaml
----------------
Pyyaml must be installed
```
sspreitzer@s900x3c:~/git/j2⟫ cat test.yaml 
---
USER: yaml-user
sspreitzer@s900x3c:~/git/j2⟫ ./j2 -y test.yaml < test.j2 
yaml-user
```