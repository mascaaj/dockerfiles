# Docker image `rdev`

Used for development work with R version 3.4.0
Basic idea for this docker file has been borrowed from  :
https://gitlab.com/jozefhajnala/dockerfiles/-/tree/master/rdev

## Main features

- R (base, 3.4.0)

R Packages (including dependencies):

- devtools 1.13.5
- testthat 2.0.0
- dplyr : 0.7.4
- ggplot2 : 2.2.1
- Hmisc : 4.1-1
- Lubridate : 1.7.2
- ggthemes : 3.4.0
- gridExtra : 2.3
- grid : 3.4.0

## Usage

To run the container and access the r console :

```
sudo docker run --name ContainerNameofChoice --it ImageName
```

Get to the bash terminal :

```
sudo docker exec -it ContainerNameofChoice bash
```
