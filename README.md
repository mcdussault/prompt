![](prompt.png)

prompt
======

Dynamic Prompt.

Usage
=====

This use `glue` to expand the function passed in, with the follwing bindings available:

-   `t` the current time, in format "%H:%M:%S"
-   `v` the version of R
-   `V` the version of R, including the svn revision
-   `u` the user name
-   `g` the github user name
-   `m` the memory currently used by R
-   `w` the current working directory

``` r
set_prompt( ~ "{t}> " )
set_prompt( ~ "{w}> " )
set_prompt( ~ "[{m}] {t} {w}> ")
```

You can use `expand_prompt` to experiment :

``` r
expand_prompt( ~ "{t}> " )
```

    ## 11:39:42>

``` r
expand_prompt( ~ "{w}> " )
```

    ## /Users/romain/git/prompt>

``` r
expand_prompt( ~ "[{m}] {t} {w}> ")
```

    ## [36 MB] 11:39:42 /Users/romain/git/prompt>

Installation
------------

    install_github( "ThinkR-open/prompt" )

Initial ideas
-------------

in a way that can be configured. Things we might want to display:

-   current time
-   memory used `pryr::mem_used`
-   current working directory, maybe slightly differently when it's not the directory of the current rstudio project
-   are we developping a package ? Do we need to rebuild it ?
-   are we sync with github
-   R version
-   ...
-   (please add your own with PR)

License
-------

MIT + file LICENSE ©
