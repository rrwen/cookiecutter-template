# cookiecutter-template

Richard Wen  
rrwen.dev@gmail.com  

Personal Python cookiecutter base template.

[![Build Status](https://travis-ci.org/rrwen/cookiecutter-template.svg?branch=master)](https://travis-ci.org/rrwen/cookiecutter-template)
[![GitHub license](https://img.shields.io/github/license/rrwen/cookiecutter-template.svg)](https://github.com/rrwen/cookiecutter-template/blob/master/LICENSE)

## Install

1. Install [Python](https://www.python.org/downloads/)
2. Install [cookiecutter](https://pypi.python.org/pypi/cookiecutter) via `pip`
3. Install [Node.js](https://nodejs.org/en/)

```
pip install cookiecutter
```

## Usage

Create a [cookiecutter](https://pypi.python.org/pypi/cookiecutter) template:

```
cookiecutter gh:rrwen/cookiecutter-template
```

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

* The main file is [cookiecutter.json](https://github.com/rrwen/cookiecutter-template/blob/master/cookiecutter.json) which defines the inputs for the command line interface
* The inputs then replace any values surrounded with `{{}}` inside the folder [{{cookiecutter.template_name}}](https://github.com/rrwen/cookiecutter-template/tree/master/%7B%7Bcookiecutter.template_name%7D%7D)

```
        cookiecutter              <-- template tool
             |
      cookiecutter.json           <-- template inputs
             |
{{cookiecutter.template_name}}    <-- generated template
```

The following files will be created inside a folder with the same name as the `template_name` input:

* **{{cookiecutter.template_name}}**: templating folder with README.md and MIT LICENSE files
* **.gitignore**: a Python [.gitignore](https://git-scm.com/docs/gitignore) automatically generated from github
* **.travis.yml**: a [.travis.yml](https://docs.travis-ci.com/user/customizing-the-build/) file for automatic builds and tests
* **LICENSE**: MIT [license file](https://help.github.com/articles/licensing-a-repository/) automatically created from github
* **README.md**: a readme [Markdown](https://daringfireball.net/projects/markdown/) file with header, install, usage, and developer notes sections
