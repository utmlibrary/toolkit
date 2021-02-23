---
layout: page
title: Introduction to the Unity Editor and Making Games
permalink: /workshops/unity/
---
## Table of Contents

1. [About](#about)  
2. [Resources](#resources)  
    2.1 [Tutorials](#tutorials)   
    2.2 [Copyright](#copyright)
3. [Setup](#setup)  
    3.1 [Install Unity Hub](#unityhub)  
    3.2 [Create Account](#unityaccount)  
    3.3 [Install Unity Editor Version](#unityversion)  
    3.4 [Install RPG Creator Kit Project](#unityproject)  
4. [Workshop: RPG Creator Kit](#workshops)  
    4.1 [The Editor Interface](#warmup)  
    4.2 [Build the Environment](#exercise1)  
    4.3 [Story Items](#exercise2)  
    4.4 [NPCs and Dialogue Trees](#exercise3)  
    4.5 [Quests](#exercise4)  
    4.6 [Build and Publish](#exercise5)
5. [Final Thoughts](#final)

Workshop by [Chris Young](mailto:christopher.young@utoronto.ca)
Last edited February 22, 2021

## 1. About <a name="about"></a>

The Unity Editor is a real-time 3D production tool for rendering photo-realistic animations, graphics, and models in an array of digital design contexts. The Editor is used across several industries, including games and cross-reality, television and film, architecture and construction, automotive, transportation, and manufacturing. As an all-in-one digital tool, the Editor contains dozens of functions and plugins to design a complete storytelling experience from initial design concept to release and distribution. Creators can synchronize graphics, animations, sounds, text, and the user interface all within the Editor. The Unity Editor is a powerful resource in the creation of digital content to create storytelling experiences for players and users.

As you can imagine, the Unity Editor can be quite useful if you are interested in building a digital storytelling experience that contains a variety of digital content. Creations with the Editor can range from 2D and 3D games to interactive fiction to animated shorts. In the documentation provided in this workshop, we only cover how you can create a role-playing game (RPG) using a pre-fabricated package of assets provided by Unity--meaning, we will show you how to make a game from beginning to end. However, Unity is incredibly robust, including the package of assets we will be using. So, while the intended length of this workshop is approximately 2 hours, you may find yourself spending dozens of hours creating additional content, designing your storytelling experience, and expanding the scale of your game's digital world. 

## 2. Resources <a name="resources"></a>
There are some fantastic resources out there to learn how to use the Unity Editor and to create engaging storytelling experiences. The most important resource to consult is the [Unity Learn Platform](https://learn.unity.com/) which provides a rich catalogue of live and asynchronous workshops to explore the Editor's functionalities, plugins, and assets. The [RPG Creator Kit](https://learn.unity.com/project/creator-kit-rpg) tutorial provided by Unity Learn will be of particular value as large parts of the tutorial are used or adapted for this workshop. A final resource to consult is the [*Elements of Game Design*](https://mitpress.mit.edu/books/elements-game-design) by Robert Zubek. The text is a very accessible and short volume on game design and will be of particular interest for creators looking to learn more about game design.

### 2.1 Tutorials <a name="tutorials"></a>
In addition to the important resources outlined above, there are a number of tutorials out there that can assist you in becoming a more proficient game designer with the Unity Editor. While there are dozens, if not hundreds, of excellent tutorials out there, these are some of resources I found to be most useful in gaining proviciency in making Unity-based games:

[Unity Learn: Getting Started with Unity](https://learn.unity.com/course/getting-started-with-unity)  
[edX: Introduction to Video Game Development with Unity](https://www.edx.org/course/introduction-to-video-game-development-with-unity)  
[Coursera: Game Design and Development with Unity 2020 Specialization](https://www.coursera.org/specializations/game-design-and-development)
[Bracekeys YouTube: Unity Beginner Tutorials](https://www.youtube.com/playlist?list=PLPV2KyIb3jR5QFsefuO2RlAgWEz6EvVi6)  
[LinkedIn Learning: Unity 3D 2019 Essential Training](https://www.linkedin.com/learning-login/share?account=76812730&forceAccount=false&redirect=https%3A%2F%2Fwww.linkedin.com%2Flearning%2Funity-3d-2019-essential-training%3Ftrk%3Dshare_ent_url%26shareId%3DLL4sq0plT7iEUdBLZYxlnA%253D%253D)

If you want to get stuck into a specific genre of game design through a project-based learning approach, I'd recommend the following tutorials:

[Interactive Fiction: inky plugin for the by Inkle Studio](https://www.inklestudios.com/ink/)  
[Walkthrough Simulator: First Person Exploration Toolkit by While Fun Games](http://whilefun.com/fpekit)  
[Platformer: Platformer Microgame by Unity Learn](https://learn.unity.com/project/2d-platformer-template)  
[First Person Shooter: FPS Microgame by Unity Learn](https://learn.unity.com/project/fps-template)  
[Roguelike: 2D Roguelike by Unity Learn](https://learn.unity.com/project/2d-roguelike-tutorial)

### 2.1 Copyright <a name="copyright"></a>
Copyright has an impact on digital storytelling projects, including the use of copyrighted assets, such as images and audio imported into Unity. Many digital storytelling experiences will use graphics and sounds from online repositories to build their game's environment. In most cases licenses are provided with the assets when they are downloaded, but it's critical that you check the asset's license terms before you use it.

Most post-secondary institutions have Scholarly Communication and Copyright offices with copyright guidelines on fair dealing. Check in with your scholarly communication and copyright office if you are not sure your data collection falls under fair dealing. For faculty, staff, and students at UTM, you can contact our [Scholarly Communication Librarian](https://utm.library.utoronto.ca/scholarly-communications) to learn more about copyright fair dealing. The University has also put together a number of resources you can consult if you need a quick-and-fast answer:

[Copyright Fair Dealing Guidelines](https://provost.utoronto.ca//wp-content/uploads/sites/155/2018/06/Copyright-Guidelines.pdf)  
[Copyright Basics](https://onesearch.library.utoronto.ca/sites/default/files/copyright/basicsfaqs_092018.pdf)  
[Copyright Road Map](https://onesearch.library.utoronto.ca/sites/default/files/copyright/utl_copyrightroadmap_february2020update.pdf)

Some other useful resources to consult on copyright fair dealing include:

Canadian Association of Research Libraries' [fair dealing documentation](https://fair-dealing.ca/what-is-fair-dealing/)  
The Writers Union of Canada's [fair dealing documentation](https://www.writersunion.ca/what-and-isn-t-fair-dealing)  
Council of Ministers of Education's [fair dealing decision tool](http://www.fairdealingdecisiontool.ca/DecisionTool/)

Note, these copyright resources only pertain to the [*Copyright Act*](https://laws-lois.justice.gc.ca/eng/acts/C-42/) for fair dealing in Canada and does not cover copyright in other jurisdictions. For international researchers please consult your own scholarly communication and copyright offices and resources on fair use or fair dealing of copyrighted works in digital research.

## 3. Setup <a name="setup"></a>
The Unity Editor operates on Windows, OS X, and Linux operating systems. The simplest way to setup the Unity Editor on your computer is to download the [Unity Hub](https://unity3d.com/get-unity/download) which manages all your projects and installations going forward. From there you can create your [Unity account](https://id.unity.com/en/conversations/01819edd-83df-48e6-91ae-d008a0ef4ed4002f) and install the correct version of the Editor to work with the RPG Creator Kit that we will be using in this workshop. You also have the option to just install a specific version of the Unity Editor. However, the organization of your Unity files can get messy if you decide to work on multiple projects, which may you require you to install multiple versions of the Unity Editor. As such, the recommended setup is the process we outline below.

### 3.1 Install Unity Hub <a name="unityhub"></a>

### 3.2 Create Account <a name="unityaccount"></a>

### 3.3 Install Unity Editor Version <a name="unityversion"></a>

### 3.4 Install RPG Creator Kit Project <a name="unityproject"></a>

## 4. Workshop: RPG Creator Kit <a name="workshops"></a>

### 4.1 The Editor Interface <a name="warmup"></a>

Familiarize with the interface

### 4.2 Build the Environment <a name="exercise1"></a>

Download and install creator kit

### 4.3 Story Items <a name="exercise2"></a>

Build the environment for the game

### 4.4 NPCs and Dialogue Trees <a name="exercise3"></a>

Create characters and dialogue trees

### 4.4 Quests <a name="exercise4"></a>

Create quests with non-player characters and objects

### 4.5 Build and Publish <a name="exercise5"></a>

How to build and publish your game.

## 5. Final Thoughts <a name="final"></a>



