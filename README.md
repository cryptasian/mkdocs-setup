# Mkdocs Setup
Adapted from the original [Mkdocs documentation].
[Mkdocs documentation]: https://www.mkdocs.org/

## Ubuntu Installation

### Python
In order to manually install MkDocs you'll need [Python] installed on your
system, as well as the Python package manager, [pip]. You can check if you have
these already installed from the command line:

```bash
$ python --version
Python 2.7.14
$ pip --version
pip 18.1 from /usr/local/lib/python2.7/site-packages/pip (python 2.7)
```

MkDocs supports Python versions 2.7.9+, 3.4, 3.5, 3.6, 3.7, and pypy.

Install [Python] by downloading an installer appropriate for your system from
[python.org] and running it.

[python.org]: https://www.python.org/downloads/
[Python]: https://www.python.org/

### Pip
If you're using a recent version of Python, the Python package manager, [pip],
is most likely installed by default. However, you may need to upgrade pip to the
lasted version:

```bash
pip install --upgrade pip
```

If you need to install [pip] for the first time, download [get-pip.py].
Then run the following command to install it:

```bash
python get-pip.py
```
[pip]: https://pip.readthedocs.io/en/stable/installing/
[get-pip.py]: https://bootstrap.pypa.io/get-pip.py

### Mkdocs
Install Mkdocs with the ubuntu package manager.

```bash
sudo apt install mkdocs
```
You can also install Mkdocs with pip if you prefer.

```bash
pip install mkdocs
```

You should now have the `mkdocs` command installed on your system. Run `mkdocs
--version` to check that everything worked okay.

```bash
$ mkdocs --version
mkdocs, version 0.15.3
```

---

## Getting Started

Getting started is super easy.

```bash
mkdocs new my-project
cd my-project
```

There's a single configuration file named `mkdocs.yml`, and a folder named
`docs` that will contain your documentation source files. Right now the `docs`
folder just contains a single documentation page, named `index.md`.

MkDocs comes with a built-in dev-server that lets you preview your documentation
as you work on it. Make sure you're in the same directory as the `mkdocs.yml`
configuration file, and then start the server by running the `mkdocs serve`
command:

```bash
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000
[I 160402 15:50:43 handlers:58] Start watching changes
[I 160402 15:50:43 handlers:60] Start detecting changes
```

Open up `http://127.0.0.1:8000/` in your browser, and you'll see the default
home page being displayed.

The dev-server also supports auto-reloading, and will rebuild your documentation
whenever anything in the configuration file, documentation directory, or theme
directory changes.

Open the `docs/index.md` document in your text editor of choice, change the
initial heading to `MkLorum`, and save your changes. Your browser will
auto-reload and you should see your updated documentation immediately.

Now try editing the configuration file: `mkdocs.yml`. Change the
[`site_name`][site_name] setting to `MkLorum` and save the file.

```yaml
site_name: MkLorum
```

Your browser should immediately reload, and you'll see your new site name take
effect.

## Adding pages

Now add a second page to your documentation:

```bash
curl 'https://jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
```

As our documentation site will include some navigation headers, you may want to
edit the configuration file and add some information about the order, title, and
nesting of each page in the navigation header by adding a [`nav`][nav]
setting:

```yaml
site_name: MkLorum
nav:
    - Home: index.md
    - About: about.md
```

## Changing the Favicon Icon

By default, MkDocs uses the [MkDocs favicon] icon. To use a different icon, create
an `img` subdirectory in your `docs` directory and copy your custom `favicon.ico` file
to that directory. MkDocs will automatically detect and use that file as your
favicon icon.

[MkDocs favicon]: /img/favicon.ico

## Building the site

That's looking good. You're ready to deploy the first pass of your `MkLorum`
documentation. First build the documentation:

```bash
mkdocs build
```

## Deploying

The documentation site that you just built only uses static files so you'll be
able to host it from pretty much anywhere. Just upload the contents
of the entire `site` directory to wherever you're hosting your website from and
you're done. 

When using Github Pages, create a new repository, create a `docs` folder, and upload the **contents** of your `site` directory. Then go to the Settings tab in the repository and scroll down until you see a Github Pages section. When picking what source you would like to use, select `master branch /docs folder` and your Github Page will be live. 

If you want to use a custom domain with Github Pages, [click here to learn more].

[click here to learn more]: https://help.github.com/articles/using-a-custom-domain-with-github-pages/
