# Lab 1 - Source to image with a Cloud Native Buildpack

## Prerequisites 

### Mac

* Install [git](https://git-scm.com/downloads)
* Install [docker](https://docs.docker.com/install/)
* Install [pack](https://buildpacks.io/docs/install-pack/)
* Install [jq]()
* Install [siege]()
* Install [dive](https://github.com/wagoodman/dive)

### Windows

@TODO

## Let's Get Started

### Clone the cnb workshop repository
This repo will contain all of the files necessary to work through the workshop labs. Clone the repository and go to its directory

```
git clone https://github.com/cf-platform-eng/cnb-workshop.git
cd cnb-workshop
```

## Lab 1

Go to the `lab-1` directory

```
cd lab-1
```

### Configure the pack CLI

Today you will be using the `pack` cli which is a tool for building apps using cloud native buildpacks

**Set the default builder:**

```
pack set-default-builder cloudfoundry/cnb:bionic
```

**What is a builder?**

A builder is an image that bundles all the bits and information on how to build your apps, such as buildpacks and build-time image, as well as executes the buildpacks against your app source code.

### Build the sample app

Go to the `sample-app` directory and run `pack build <image-name>`

```
cd sample-app
pack build sample-app
```

### Run the sample app with Docker

```
docker run -it -p 8080:8080 sample-app
```

### Check out the app

Now visit `http://localhost:8080/actuator/env` in your browser to see the app running.