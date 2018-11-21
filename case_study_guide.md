# Titanic & Python Data Stack Case Study

This case study highlights best practices and workflows, in a format that is common in industry. While there are many 
(strongly opinionated) style guides and best practice recommendations, there is currently no industry standard code 
repository format or universal data science workflow. 

Instead, this code base highlights a few ways to 'raise the bar' in your own work, and good defaults to follow while 
getting your sea legs. For the best experience, have a look at:

 - `README.md`
 - `bin/main.py` 

Common components of a data science project include:

## `README.md`

The primary communication between the code's author and the world, the `README.md` file (or less commonly `README.txt` 
or `README.rst`) file is the 'at-a-glance' description of the code base. It generally describes:

 - Project purpose
 - How to run the code
 - Any unusual design choices, or design considerations the user / audience should be aware of

## Code files

### `.py` file
While most Python lessons are in Jupyter notebooks, `.py` files (also known as scripts, source files or python files) 
are very common, and generally preferred for production projects and larger code bases. 

### Code style

The Python community has largely centered around two style guides:

 - [PEP-8](https://www.python.org/dev/peps/pep-0008/): The official Python style guide, which provides more bare-bones 
 instructions for writing maintainable, consistent code
 - [The Google Python Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md): Google's internal 
 Python style guide, which is also very popular outside of Google. This guide provides more in-depth and actionable 
 instructions.    

### Folder structure

It is common to either have files in the repo's root directory, or to use the following folders:

 - `bin`: For any executable files (e.g. `.py` or `.sh`)
 - `conf`: For any configuration files (e.g. credentials for connecting to a database)
 - `docs`: For any documentation
 
Generally, a file named `main.py` will be the primary entry point to your code base, and running this file will allow 
users to use your product. 

## Package management

Occasionally, your project will require python packages not found in the 
[Python Standard Library](https://docs.python.org/3/library/) or [Anaconda included package list](https://docs.anaconda.com/anaconda/packages/pkg-docs/). 
In these cases, we should specify to the user which package and package version to install. There are two common ways of
specifying these additional packages:

 - [`requirements.txt`](https://pip.readthedocs.io/en/1.1/requirements.html): This file is installed using pip 
 (i.e. `pip install -r requirements.txt`), and will specify the files to include
 - [`environment.yml`](https://conda.io/docs/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file): This
 file is installed using Anaconda (i.e. `conda env create -f environment.yml`), and includes some information in 
 addition to the information in `requirements.txt` 