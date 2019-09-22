# houdini-pdg-intro-notes

Notes repository for Houdini PDG that also includes some examples.

## Introduction

### Potential Applications of PDG

| Inside Houdini | Outside Houdini |
| -------------- | --------------- |
| Wedging Particles | Photogrammetry Pipeline |
| Creating and Updating a City | Assembling Characters |
| Creating Endless Landscapes | Machine Learning |
| Parallelizing Sequential Workflows | Automating & Scaling Entire Pipeline |

### What is PDG?

PDG stands for Procedural Dependency Graph
PDG describes complex dependencies visually with nodes
PDG transforms that dependency description into a set of actionable, scheduable tasks
Distributes those tasks with the help of a scheduler and computes them in parallel

PDG can be broken up into a list of functions that produce a list of results.  These lists can be automated to run thousands of times.  PDG replaces the 1-to-1 processing to a 1-to-many processing.  

PDG also allows the distribution of processes across resources on the computer.  Processes can be handled in parallel across resources on the computer.  A scheduler ensures that tasks are being processed.

Houdini contains different _schedulers_ that can perform processes locally or across resources in other networks, on the cloud, or custom scheduling through Python scripts.

_Work Items_ are single instances of each process that is to be performed.  These items can be handled in parallel independent of other works items being processed.

PDG keeps track of each work item and determines if it is finished, in-process, or back-logged.  Back-logged means that the node is waiting for additional dependencies to be completed before it can be worked on.  Back-logged tasks can additionally be broken into awaiting upstream results or waiting for computer resources to be completed.

Each PDG network has a _Task Graph_ which outlines the status of each work item.  A selected node can show the connections to each upstream work item.

The _Task Info_ panel will show all the information required to analyze the processing of the task item.

### Setting Up a Simple Top Network

**This section will follow the Spatial Coloniation Network from the tutorial**

### How does Space Colonization Work?

| Input Text File | Create 3D Type | Convert to Volume | Scatter Food and Seed | Seed Searches for Food, Consume Food, and Grows Branches |
| --- | --- | --- | --- | --- | --- |

At the object level:

1) Food and Seed Generator
2) Spatial Colonization Generator
3) Render Line Thickness

TOP networks help you with creation of PDG networks.  

The _File Glob_ node **now Files From Pattern** node to import files.

For more information on space colonization.. go to: http://algorithmicbotany.org/papers/colonization.egwnp2007.large.pdf