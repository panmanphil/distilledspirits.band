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

you may need to remove it first
```
git submodule deinit -f themes/ananke
git rm themes/ananke
```
remove it from the index
`git rm -f themes/ananke`
remove from the git metadata
`rm -rf .git/modules/themes/ananke`
edit `.gitmodules` as well to clean up as needed

commit to git as desired now

### adding submodule back for the theme
```
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
git submodule update --init --recursive
```

we should now be at the current tip of the main branch for the theme

### running
normally it is just `hugo server` from the root of the project
when there are wierd cache like issues `hugo server --ignoreCache --disableFastRender`
you can also delete the `public` folder

# building into the public folder
`hugo --baseURL https://distilledspirits.band`

# deploy to AWS (assumes aws client is setup and logged in)
`aws s3 sync public s3://distilledspirits.band`