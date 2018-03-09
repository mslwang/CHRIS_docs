# ChRIS

## Abstract
This page presents a quick overview to ChRIS, followed by some links to more resources, papers, and talks.

## Overview
ChRIS (ChRIS Research Integration Service) is a novel and opensource software framework designed to manage and coordinate computation and data on a multitude of environments, from laptops to loosely connected groups of workstations, to high performance compute clusters, to public clouds.

ChRIS comprises a collection of REST-based services, backend web apps, and various client-facing front ends. The system is designed to make it as *easy* as possible for a developer to get his/her app running *anywhere*. By conforming to a reasonable command-line standard for applications, ChRIS makes it easy to dockerize and then run research 

## Need

Computational research in scientific (as opposed to industry) medical-related fields faces many obstacles, including (but not limited to):

* data sharing
* data protection
* algorithm/program sharing
* re-use of existing programs in different environment
* access to powerful hardware

## Existing solutions

Cloud resources are available from private and public companies -- Amazon, Microsoft, Google, etc. In many contexts, these resources are geared to web-based service provision and not ideal for running an app that simply crunches data and creates an output.

Not only is there a cost involved to using these services, but the barrier to entry is arguably quite high. Running a simple app that takes an input and creates an output often requires complex setup and re-thinking of how the app can fit within a generalized web-services computational model.

Finally, none of the mentioned services allow an end user to re-create that cloud locally for development / debugging. An end user cannot download a "mini-AWS" and run on their local hardware, for example.

## Enter ChRIS

ChRIS exists as a github repo and can be downloaded and instantiated with a few commands. On a local computer, this will download all the necessary services and provide a fully working system that is ready to service client commands.

With some minor additional work, specific micro-services can be instantiated on different computers, and ChRIS can coordinate data and compute between all these computers.

## Quick deep dive -- backend

The main backend engine of ChRIS, called CUBE (ChRIS Ultron Back-End) is a python django app that provides databasing and services relating to a collection+json REST API.

CUBE in turn "talks" to a coordinating service called ``pfcon``, which  is the dispatching service between CUBE and an actual computational environment. In this environment, two additional services are required to exist and be http accessible: ``pman`` that does process management, and ``pfioh`` that handles data IO.

A companion client app called ``pfurl`` can be used to communitate with all of these services.

## Quick deep dive -- frontend

There are many possible frontends to ChRIS. In fact, any program that consumes the ChRIS REST API can construct a tailor made experience.

An official front end is currently in active development, see the talk links for more info.

Visualization of medical formatted image data is provided by two projects that have been developed inhouse

* xtk 
* ami

## More Info

Some papers on ChRIS:

## Recent Talks

Some recent talks on ChRIS (please note there is much recycling on content below! I've added a quick note to the time length as a partial guide):

[http://slides.com/debio/deck-6-7-8-12-13-19-22] NA-MIC Jan 2018 Project week talk (30 minutues)
[http://slides.com/debio/deck-6-7-8-12-13-19] Massachusetts Open Cloud (5 minutes)

## Programming Links

Links to ChRIS components:

