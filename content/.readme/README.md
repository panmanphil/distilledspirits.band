## caveates and notes

### overrides of the default theme
There are a number of overrides in place. To have the home page show just a couple of underlying pages, they are in a 
folder called `front-pages`. Other content is under `pages`. `pages` has a subdirectory, `house-concerts` for specific house 
concert information. For some reason, hugo is treating this as a bundle and ignoring the `layouts/single.html` file for 
reasons unknown. That file has been duplicated under `layouts/pages/single.html`. The main idea of that override is to suppress
the folder, title and modified date that the theme automatically supplies since these are
already part of the header

### hugo version
currently at .159.0 

# ananke version
This is from the main branch, and must be loaded as a git submodule. when reloading from github, the module is not included

