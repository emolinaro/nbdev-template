# nbdev template

Use this template to create nbdev projects.

## Requirements

- nbdev
- jupyter

## Update project settings

Edit the mandatory fields in the file `settings.ini`. Once the file `settings.ini` is updated, run the commands:
```bash
nbdev_install_git_hooks
nbdev_build_lib
```
A new folder is created with the name specified by the `lib_name` field in `settings.ini`. 

## Install modules

All project dependencies should be installed locally by running the following the command in the project root:
```bash
pip install -e .
```
In this way all the modules will be installed in the environment in editable mode.

## Create the documentation

To enable documentation inside GitHub repo, click 'Settings' on the main repo page, scroll down to 'GitHub Pages', and under 'Source' choose 'master branch /docs folder'. GitHub will then show you a link to your working documentation site.

The file `nbs/index.ipynb` is converted into the project _README_ file. To create the documentation, run the command:
```bash
nbdev_build_docs
```
This will export HTML versions of the notebooks located in the `nbs` folder to the `docs` directory, and will create hyperlinks for any words in backticks (as long as they exist in your module). It will also create a menu for all notebooks you have created, and a table of contents for each.
