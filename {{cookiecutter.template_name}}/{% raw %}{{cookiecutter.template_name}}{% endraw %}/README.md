# {% raw %}{{cookiecutter.template_name}}{% endraw %}

{% raw %}{{cookiecutter.author}}{% endraw %}  
{% raw %}{{cookiecutter.email}}{% endraw %}  

{% raw %}{{cookiecutter.template_description}}{% endraw %}.

[![Build Status](https://travis-ci.org/{% raw %}{{cookiecutter.github_short}}{% endraw %}.svg?branch=master)](https://travis-ci.org/{% raw %}{{cookiecutter.github_short}}{% endraw %})
[![GitHub license](https://img.shields.io/github/license/{% raw %}{{cookiecutter.github_short}}{% endraw %}.svg)](https://github.com/{% raw %}{{cookiecutter.github_short}}{% endraw %}/blob/master/LICENSE)

## Install

1. Install [Python](https://www.python.org/downloads/)
2. Install [cookiecutter](https://pypi.python.org/pypi/cookiecutter) via `pip`

```
pip install cookiecutter
```

## Usage

Create a template using [cookiecutter](https://pypi.python.org/pypi/cookiecutter):

```
cookiecutter gh:{% raw %}{{cookiecutter.github_short}}{% endraw %}
```

## Developer Notes

### Create Github Repository

1. Ensure [git](https://git-scm.com/) is installed
2. Change directory to the generated folder `cd <template_name>`
3. Initialize the repository
4. Add the generated files to commit
5. Create a [Github repository](https://help.github.com/articles/create-a-repo/) with the same name as `template_name`
6. Push the commit from `4.` to your created Github repository

```
git init
git add .
git remote add origin git@github.com:<github_user>/<template_name>
git push -u origin master
```

### Implementation

This template to create folders and files for [cookiecutter](https://pypi.python.org/pypi/cookiecutter) templates.

* The main file is [cookiecutter.json](https://github.com/rrwen/cookiecutter-npm/blob/master/cookiecutter.json) which defines the inputs for the command line interface
* The inputs then replace any values surrounded with `{{}}` inside the folder [{% raw %}{{cookiecutter.template_name}}{% endraw %}]({% raw %}{{cookiecutter.github_url}}{% endraw %}/tree/master/%7B%7B{% raw %}{{cookiecutter.template_name}}{% endraw %}%7D%7D)

```
        cookiecutter             <-- template tool
             |
      cookiecutter.json          <-- template inputs
             |
{% raw %}{{cookiecutter.template_name}}{% endraw %}    <-- generated template
```

The following files will be created inside a folder with the same name as the `template_name` input:

* **.gitignore**: a Python [.gitignore](https://git-scm.com/docs/gitignore) automatically generated from github
* **.travis.yml**: a [.travis.yml](https://docs.travis-ci.com/user/languages/javascript-with-nodejs/) file for automatic builds and tests
* **LICENSE**: MIT [license file](https://help.github.com/articles/licensing-a-repository/) automatically created from github
* **README.md**: a readme [Markdown](https://daringfireball.net/projects/markdown/) file with header, install, usage, and developer notes sections
