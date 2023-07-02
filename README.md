# Chromotons Blog

## Editing

Run

````bash
git clone --recurse-submodules git@github.com:Chromotron/chromotron.github.io.git
````

to automatically initialize the theme submodule while cloning. Then commit and push your changes normally.

## Updating the theme

````bash
git submodule update --remote
````

Then record the change by creating a new commit. When others pull the commit they will have to run 

````bash
git submodule update --init --recursive
````

to make sure they actually get all changes to the submodules. [^1]



[^1]: https://git-scm.com/book/en/v2/Git-Tools-Submodules