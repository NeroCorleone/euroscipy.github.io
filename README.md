# Site `euroscipy.org`

[![](https://github.com/euroscipy/euroscipy.github.io/workflows/Publish%20Github%20Pages/badge.svg)](https://github.com/euroscipy/euroscipy.github.io/actions?query=workflow%3A%22Publish+Github+Pages%22)

This repository contains the landing page and blog for the site
[euroscipy.org](euroscipy.org).

**Note:** This repository has submodules, clone with:

```bash
git clone --recursive <git_url>
```

## Create dev environment with Conda

```bash
conda create -n pelican python=3.7
conda activate pelican
conda install pip
git clone --recursive <git_url> <dest>
cd <dest>
pip install -r requirements.txt
```

## Contributing

Currently the website is a set of static pages generated by
[Pelican](http://getpelican.org). The generated content is uploaded
to our server sponsored by [Enthought](http://enthought.com). Contact
[euroscipy-org@python.org](mailto:euroscipy-org@python.org) to
get things updated.

Please feel free to contribute in what ever capacity you feel best.
For now, the site contains details for conferences past and news items
from conferences.

Here are a few ways you can contribute:

### Add news item

* [Fork the repository](https://help.github.com/articles/fork-a-repo) on
  [GitHub](https://github.com/euroscipy/www.euroscipy.org)

* [Clone the fork](https://help.github.com/articles/fork-a-repo#step-2-clone-your-fork)

```bash
git clone --recursive git@github.com:euroscipy/www.euroscipy.org.git
cd www.euroscipy.org
```

* [Create a new branch](https://help.github.com/articles/fork-a-repo#create-branches) with the name of your news item.

* Add your news item in content/news, see
  [Pelican docs](http://docs.getpelican.com/en/stable/content.html#writing-content)
  for details can be rst or markdown. An example below:

```bash
$ cd content/news
>
$ cat << EOF > 2013-10-25-test.md
> Title: Test
> Date: 2013-10-25
> Comments: true
> Categories:
> Author: Andy R. Terrel <andy.terrel@gmail.com>
> Summary: Testing
>
> Testing how this works!
>
> EOF
```

* [Push to your fork on GitHub](https://help.github.com/articles/fork-a-repo#push-commits)

* [Create a pull request](https://help.github.com/articles/using-pull-requests)

* Email [euroscipy-org@python.org](mailto:euroscipy-org@python.org) to get the content deployed.

### Add or edit a page

* To edit the website one needs to first install the pelican blog system, see
  [Pelican Quickstart](http://docs.getpelican.com/en/stable/quickstart.html)
  * be sure to have [Markdown](http://pythonhosted.org/Markdown/index.html) installed as well

* Next checkout the source code:

```bash
git clone git@github.com:euroscipy/euroscipy.github.io.git
cd euroscipy.github.io
```

* Editing pages:

  * The content of the page can be found in the content directory

  ```bash
  $ cd content; ls
  > pages static
  ```

  * `static`: content to be copied,
  * `pages`: the set of pages to be displayed

  * To add a new post, add a file to the news, see pelican docs for the page issues

* Generating and viewing changes
  * Now go to the top dir and regenerate site:

  ```bash
  cd ../../
  make html
  ```

  * To view it locally:

```bash
$ make serve
>
< open browser to http://127.0.0.1:8000 >
( you should see your test page in the News and archives )
< Ctrl-C to exit server on terminal >
```

* To create a dev server that reloads content automatically:

```bash
$ make devserver
>
< open browser to http://127.0.0.1:8000 >
( you should see your test page in the News and archives , only works for python <= 3.7)
< Ctrl-C to exit server on terminal >
```

* To modify a page edit inside the pages content

```bash
cd content/pages
vi 2018/index.md
```

* Once again go to top and make it and view

```bash
cd ../.. && make html && make serve
```

* To edit the layout see thing inside the theme

  ```bash
  ls theme
  > tuxlite_zf
  ```

  * Be sure to check in your changes and push

  ```bash
  git add <files changed>
  git commit -m “<Describe changes>”
  git push origin <branch-name>
  ```

## Contact

The site is collaboratively edited by the SciPy Organizers.  Please
email <euroscipy-org@python.org> for details.
