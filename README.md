# nbdev template

Use this template to create Python modules with [`nbdev`](https://nbdev.fast.ai/).

## Requirements

- nbdev
- jupyter

## Update project settings

Edit the mandatory fields in the file `settings.ini`. Once the file `settings.ini` is updated, run the commands:
```bash
nbdev_install_git_hooks
nbdev_build_lib
```
A new folder is created with the name specified by the `lib_name` section in `settings.ini`. 

If the project requires other modules as dependencies, these can be added to `settings.in` using the `requirements` section. 

## Install prerequisites

All project dependencies should be installed in the local environment _in editable mode_, by running the following the command from the repo root folder:
```bash
pip install -e .
```

## Create the documentation

To enable documentation inside GitHub repo, click 'Settings' on the main repo page, scroll down to 'GitHub Pages', and under 'Source' choose 'master branch /docs folder'. GitHub will then show you a link to your working documentation site.

The file `nbs/index.ipynb` is converted into the project _README_ file. To create the documentation, run the command:
```bash
nbdev_build_docs
```
This will export HTML versions of the notebooks located in the `nbs` folder to the `docs` directory, and will create hyperlinks for any words in backticks (as long as they exist in your module). It will also create a menu for all notebooks you have created, and a table of contents for each.

### View Documentation locally

To install the modules needed for serving nbdev docs run the commands:
```bash
cd docs
bundle install
```
Then, from the repo root folder:
```bash
make docs_serve
```
This will launch a server on port 4000 (by default) which you can connect to with your browser to view your docs.

If Github pages fails to build your docs, running locally with Jekyll is the easiest way to find out what the problem is.





