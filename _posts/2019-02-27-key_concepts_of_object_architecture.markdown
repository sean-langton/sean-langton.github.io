---
layout: post
title:      "Key Concepts of Object Architecture"
date:       2019-02-27 18:04:48 +0000
permalink:  key_concepts_of_object_architecture
---


The main organizing principal of object-oriented architecture is to organize code based on how data is structured as oppose to the logic to interact with the data. Before object-oriented programming, programs were often written as simple linear flows based on how the user might interact with the program. To perform a loop, a specific block of code would be referenced. And while this is fine in the days of BASIC and software run on a single computer, with the advent of the internet and programs more often than not interacting data structures or programs outside itself, the ability to engage with only specific components of a larger architecture becomes increasingly important. It also increases the ease at with large teams can develop independently within the same architecture.

![Example of Referencing Blocks of Code](https://i.imgur.com/pnyrhoC.jpg)

Objects in a Object-Oriented architecture should only contain data related to itself. An instance of a user might contain it's name and address, but not the address of it's neighbor. The address of it's neighbor should be contained in a different instance of a user, and a different class should be created for the building to map their relationship. The advantages of this type of structure it that it allows one to more easily add or update data with minimal resources being used. It also allows for the ability to limit or grant access to certain data based on a user properties. 

There's also the ability to create new classes that inherit properties for other classes. This minimizes the amount of code for classes that share common characteristics but require unique properties or methods. This increasing the ability to run DRY code and the efficency of the developer on the project.


