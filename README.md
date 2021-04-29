# Spelman Innovation Lab Documentation

Built using MkDocs.

##Installing MkDocs
`pip install mkdocs`


##Getting Started
```
mkdocs new my-project
```

There's a single configuration file named mkdocs.yml, and a folder named docs that will contain your documentation source files.

##Start the MkDocs Server
```
cd my-project
mkdocs serve
```

Now, open up `http://127.0.0.1:8000/` in your browser.


##Configuration
There's a single configuration file named `mkdocs.yml`, and a folder named `docs` that will contain your documentation source files.

#Building the site
```
mkdocs build
```

##You can (and should) also test your site against a generic local server after building the site

Navigate to the top level level of the build directory.  This should contain your `index.html` file.  Now start a local server:

```
python3 -m http.server 1234
```

Now view the site at `localhost:1234` in your browser.
