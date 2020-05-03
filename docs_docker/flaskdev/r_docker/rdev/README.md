# Docker image `rdev`

Used for development work with R version 3.4.4.

## Main features

- R (base, 3.4.4)

R Packages (including dependencies):

- roxygen2 6.0.1
- devtools 1.13.5
- testthat 2.0.0
- covr 3.0.1
- knitr 1.20
- rmarkdown 1.9

## Usage

Interactive with R

```
sudo docker run --rm -it jozefhajnala/rdev:3.4.4 R
```
