<p align="center">
  <img src="./source/images/RevMsgLogo.png" alt="Slate: API Documentation Generator" width="226">
  <br>
</p>

<p align="center"><img src="./source/images/template_screenshot.png" width=700 alt="Screenshot of Example Documentation created with Slate"></p>

<p align="center"><em>The example above was created with Slate. Check it out at <a href="https://lord.github.io/slate">lord.github.io/slate</a>.</em></p>

# Introduction

This is a template for API documentation for anything publicly and internally exposed in Revere. It is based on [slate](https://github.com/lord/slate). 

# Purpose 
This exists to create a consistent api doc between all revere products. We can own this documentation. 


# Contributing
Please feel free to contribute and follow the development setup below! **Fork this repo please!**

# Development Setup 

First clone this project 

```
git clone https://github.com/revolution-messaging/revere-api-documentation-template.git && cd revere-api-documentation-template
```

Then rename origin to `upstream`

```
git remote rename origin upstream
```

and add your documentation repo to `origin`

```
git remote add origin <your repo url>
```

A Dockerfile, and a docker-compose files are provided for setting up and running a development environment. If you're familiar with docker you can skim over the details.

## Setup & Installation

Install docker from [here](https://docs.docker.com/engine/installation/) for your system. You should now also have docker-compose in your command terminal. 

Ensure docker is running the background on your machine then we can start the build.

```
docker-compose up
```
to start the application. Then visit `localhost:4567` to ensure the application is running.

# Build Deployment

Before pushing documentation to a repository please build and commit the build folder as well. We can then pull from this folder across all documentation to get the latest updates.

To build your documentation with docker run:

```
docker run --rm -v $PWD:/usr/src/app/source -w /usr/src/app/source <docker app name from docker ps> bundle exec middleman build --clean
```

## Updating The Docs 

This repo is to be kept up to date with the Slate documentation framework. To update an application document you merge this repo's changes with _your_ __master__ branch via 

```
git fetch upstream
```

then ensure master via

```
git checkout master
````

and finally 

```
git merge upstream/master
```

and once you are done you can push to origin via 

```
git push origin master
```