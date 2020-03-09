# ByThePowerOf.github.io - WIP

## Introduction

This organisation provides a suite of tools to run `make` inside a kubernetes cluster

Use cases are:
* deploy kubernetes resources
* run batch processing
* scale manager/node processing

The system can be run with a controller per namespace to provide separation for multi-tenanted clusters
Seperate components can be deployed using different service accounts.

The idea is to be declarative as the logical unit of work is a docker image and the operation is baked into the YAML of the CRDs

## Components

### [Pymake](https://github.com/bythepowerof/pymake)

A reimplementation of make in python - borrowed from [mozilla](https://github.com/mozilla/pymake)
This is useful as you can turn makefiles into YAML - so it can form part of a custom resource.

This is not perfect as pattern rules don't convert correctly. It will expand the rules rather than keep the patterns

### [kmake-controller](https://github.com/bythepowerof/kmake-controller)

A set of CRDs and controllers using [kubebuilder](https://github.com/kubernetes-sigs/kubebuilder)

### [gqlgen-kmakeapi](https://github.com/bythepowerof/gqlgen-kmakeapi)

A GQL server over the top of kmake-controller to manage and query the resources

### [kmake_gql_client](https://github.com/bythepowerof/kmake_gql_client)

A GQL client written in python to call gqlgen-kmakeapi

### [demo-wordpress](https://github.com/bythepowerof/demo-wordpress)

A wordpress exammple to deploy with kmake

### [make-kubectl](https://github.com/bythepowerof/make-kubectl)

A docker image with kubectl, make and kustomize

## Dockerhub

Not necessarily up to date [https://hub.docker.com/orgs/bythepowerof/repositories]

## To do

* An integrated example
* write tests for controller
* Documentation
* Add more schedulers to kmake-controller



