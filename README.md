[![DOI](https://zenodo.org/badge/000000000.svg)](https://zenodo.org/badge/latestdoi/000000000)

# Dynamic Punk Papers

This repo is a generic template to create Dynamic Papers Papers. 

# Why?  

We believe that science 

# How? 

Periodic updates ... All versions are stored in Zenodo [10.0000/zenodo.0000000](https://doi.org/10.0000/zenodo.0000000) so changes over time can be tracked.  

# But how?  

This repo is hosted in github and uses github actions (`/.github/workflows/publish.yml`) to trigger the document update. To build the webpage we used Quarto (`.qmd` files + `_quarto.yml`). To ensure consistency in package versions we use Renv packge (using `init()` to set up the R dependency management and `snapshot()` to update it).

To set up the github actions we first created a gh-pages branch for deployment (`quarto publish gh-pages` in terminal; details [here](https://quarto.org/docs/publishing/github-pages.html)) and connect it to github (on github `Settings/Pages/Deploy from branch/gh-pages/(root)`). You also need to add a `.nojekyll` empty file in the root and gitignore `/.quarto/` and `/_site/`. We scheduled the github action to ran once a month using `cron` but it can be triggered manually from the webpage. Note that you can also re-build the webpage manually (`quarto publish gh-pages` in terminal). Also, R scripts ran on a server, as specified in the quarto and github actions ylm´s thanks to `Renv` package and github computer time generosity. Everything is licenced with a MIT licence (`LICENCE`), which seems punky enough. 

# Notes
If actions are triggered `on: push: branches: main` (they are not right now) you can skip continuous integration in the commit message by adding `[skip ci]`   