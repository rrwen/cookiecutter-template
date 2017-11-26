# {{cookiecutter.template_name}}

{{cookiecutter.author}}  
{{cookiecutter.email}}  

{{cookiecutter.template_description}}.

[![Build Status](https://travis-ci.org/{{cookiecutter.github_short}}.svg?branch=master)](https://travis-ci.org/{{cookiecutter.github_short}})
[![GitHub license](https://img.shields.io/github/license/{{cookiecutter.github_short}}.svg)](https://github.com/{{cookiecutter.github_short}}/blob/master/LICENSE)

## Install

1. Install [Python](https://www.python.org/downloads/)
2. Install [cookiecutter](https://pypi.python.org/pypi/cookiecutter) via `pip`

```
pip install cookiecutter
```

## Usage

Create a template using [cookiecutter](https://pypi.python.org/pypi/cookiecutter):

```
cookiecutter gh:{{cookiecutter.github_short}}
```

See [Implementation](#implementation) for more details.

## Developer Notes

### Create Github Repository

1. Ensure [git](https://git-scm.com/) is installed
2. Change directory to the generated folder `cd <template_name>`
3. Initialize the repository
4. Add the generated files to commit
5. Create an empty [Github repository](https://help.github.com/articles/create-a-repo/) with the same name as `template_name`
6. Pull any changes if the Github repository is not empty
7. Push the commit from `4.` to your created Github repository

```
git init
git add .
git commit -a -m "Initial commit"
git remote add origin https://github.com/<github_user>/<template_name>.git
git pull origin master --allow-unrelated-histories
git push -u origin master
```

### Implementation

This code creates folders and files for [cookiecutter](https://pypi.python.org/pypi/cookiecutter) templates.

* The main file is [cookiecutter.json](https://github.com/rrwen/{{cookiecutter.template_name}}/blob/master/cookiecutter.json) which defines the inputs for the command line interface
* The inputs then replace any values surrounded with `{% raw %}{{}}{% endraw %}` inside the folder [{% raw %}{{cookiecutter.template_name}}{% endraw %}]({{cookiecutter.github_url}}/tree/master/%7B%7B{% raw %}{{cookiecutter.template_name}}{% endraw %}%7D%7D)

```
        cookiecutter              <-- template tool
             |
      cookiecutter.json           <-- template inputs
             |
{% raw %}{{cookiecutter.template_name}}{% endraw %}    <-- generated template
```

The following files will be created inside a folder with the same name as the `template_name` input:

File | Description
--- | ---
**LICENSE** | MIT [license file](https://help.github.com/articles/licensing-a-repository/) automatically created from github
**README.md** | a readme [Markdown](https://daringfireball.net/projects/markdown/) file with header section
