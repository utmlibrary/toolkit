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

If you want to get stuck into a specific genre of game design through a project-based learning approach in Unity, I'd recommend the following tutorials:

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
The Unity Editor operates on Windows, OS X, and Linux operating systems. The simplest way to setup the Unity Editor on your computer is to download the [Unity Hub](https://unity3d.com/get-unity/download) which manages all your projects and installations going forward. From there you can create your [Unity account](https://id.unity.com/en/conversations/01819edd-83df-48e6-91ae-d008a0ef4ed4002f) and install the correct version of the Editor to work with the RPG Creator Kit that we will be using in this workshop. You also have the option to just install a specific version of the Unity Editor. However, the organization of your Unity files can get messy if you decide to work on multiple projects, which may you require you to install multiple versions of the Unity Editor. As such, the recommended setup is the process outlined below.

### 3.1 Install Unity Hub <a name="unityhub"></a>
The Unity Hub is a management tool to you can use to manage all of your installations and projects. This includes managing all the components, like plugins, and the various versions of projects you have saved. If you decide to learn other features of Unity or work on new projects, it is likely you will have to install other asset packages and Editor versions. The Unity Hub makes this simple and also informs you if there are any issues with your installations and projects, which may not be obvious if you run multplie projects and versions outside of the Hub.

To install the Unity Hub you can download it from this [link](https://unity3d.com/get-unity/download). Click on the option ```Download Unity Hub```. The corresponding package file for your computer will download. Once downloaded, open the file, read through the Terms of Service, and agree to the Terms. Once agreed, click ```Install``` and open the Unity Hub upon completion. 

### 3.2 Create Account <a name="unityaccount"></a>
Once you have opened the Unity Hub, you will need to create a Unity Account. The main reason you need to do this is because Unity Technologies, the company of Unity's products, will not let you use their services without agreeing to their Terms of Use and Privacy Policy. For example, you will need an account to download a version of the Unity Editor and you will need an account to download any project packages or assets from the Unity Asset Store, which we will do in this workshop. As such, it is important you do not skip this step as it will cause problems for you in the next two steps.

One of the benefits of having a Unity Account is it will manage your projects, installs, and assets on your computer through the Unity Hub, but it will also keep track of any assets you download or purchase from the Unity Asset Store. This means if you decide to work on your projects on another computer you will not lose assets you have downloaded or purchased in the past.

To create a Unity Account go to this [link](https://id.unity.com/en/conversations/01819edd-83df-48e6-91ae-d008a0ef4ed4002f). You will be given the option to sign-in if you already have a Unity Account, but if this is your first time you will be asked for an Email account, Password, Username, and your Full Name. You will be given the option to read the [Unity Terms of Service](https://unity3d.com/legal/terms-of-service?_ga=2.215215761.706976237.1614087676-1693053554.1614087676) and the [Unity Privacy Policy](https://unity3d.com/legal/privacy-policy?_ga=2.215215761.706976237.1614087676-1693053554.1614087676). Once you have read through the Terms and Policy you are required to check the box before finally creating your account. 

Once you have created your Unity Account you will use your credentials to sign-in to the Unity Hub which you can do by clicking on the avatar icon in the top-right corner of the Hub. When you have successfully signed-in we can install the Unity Editor version for the RPG Creator Kit Project.

### 3.3 Install Unity Editor Version <a name="unityversion"></a>
The Unity Editor has gone through numerous iterations since it was first released in 2005. The [Download Archive](https://unity3d.com/get-unity/download/archive) provides versions of Unity stretching back to Unity 3 in 2011. Since 2017, Unity has released a significant feature version of the Unity Editor each year, labelled by the year in which it was released (e.g., "Unity 2020"). Once each year has cycled through its development phase Unity Technologies releases a final Long Term Support (LTS) version, which will be maintained as the official version of that Unity Editor. For example, since 2017 there has been a Unity 2017 (LTS), a Unity 2018 (LTS), and a Unity 2019 (LTS). As of writing, there is no Unity 2020 (LTS) version as Unity Technologies is still developing the 2020 Unity Editor and is yet to release the 2021 Unity Editor.

For this workshop, we will be downloading the latest version of the Unity Editor which is required to use the RPG Creator Kit Project. However, the latest version may change by the time you read this documentation and a different version of the Unity Editor may support the RPG Creator Kit Project. As such, the best way to know which version of the Unity Editor supports the project or assets you want to use is by viewing the ```Learn``` tab in the Unity Hub or by viewing the specific webpage of the asset in the [Unity Asset Store](https://assetstore.unity.com/). For example, the RPG Creator Kit Project is available in both the ```Learn``` and the Asset Store. As we will download the Creator Kit in the ```Learn``` section of the Hub that is where we will get our Editor version information, but you can also view the Editor version in the Asset Store at this [link](https://assetstore.unity.com/packages/essentials/tutorial-projects/creator-kit-rpg-149309). You will notice if you visit the Asset Store that it says ```Supported Unity Versions 2019.1.0 or Higher```. This means that you could download the Unity 2019 (LTS) version and it would work with Creator Kit. I mention this because when you download the current corresponding version for the Creator Kit, it is likely you will not need to install a new version of the Creator Kit in the future. So, if you decide to work on your project in the next few months, the current version you have will function accordingly.

To download the current version of the Unity Editor that functions with the RPG Creator Kit Project, click on the ```Learn``` tab and scroll down through ```Projects``` until you reach the ```Creator Kit: RPG``` project. Click on the ```Creator Kit: RPG``` and a new window will open. You will notice that the window will have a message that says something like ```You need to install Unity XXXX.X to open this project``` (XXXX.X referring to the current version of the Unity Editor that supports the Creator Kit). At the time of writing this was Unity 2020.2. You will also notice an option to ```Install Unity XXXX.X```. Click on ```Install Unity XXXX.X```.

A new window will open that will ask you to add modules to this version of the Unity Editor. You will have the option to add ```Platforms```, ```Documentation```, ```Language Packs```, and ```Dev Tools```. At this point it is recommended that you only select the appropriate developer tools for your system (e.g., Microsoft Visual Studio on PC) and the documentation. The main reason is if you select any of the platform options you will have to download additional gigabytes of modules that you do not require for this workshop. You can always go back and install addition modules in the future if you decide to build your game into an application for another system. The developer tools and documentation will be needed to get your project going and will be useful if you decide to work on other Unity Learn projects.

Once you have selected the appropriate ```Dev Tools``` and ```Documentation``` you can click next and agree to the Terms and Conditions. Depending on your computers speed, it can take around 2-10 minutes to install the Editor. 

### 3.4 Install RPG Creator Kit Project <a name="unityproject"></a>
Once you have installed the the appropriate Unity Editor, we can then install the RPG Creator Kit Project. Similar to the previous section's instructions, click on ```Learn``` in the Unity Hub and scroll down to the ```Creator Kit: RPG``` project. Click on the ```Creator Kit: RPG``` project and select ```Download Project```. When the project is has finished downloading, which can take a few minutes depending on your internet's bandwidth, click ```Open Project```.

The first time you open a project it can take several minutes for the project to configure with your version of the Unity Editor. This is nothing to be concerned about as it can potentially take 10 minutes to open, depending on your computers RAM speed (i.e., the memory processor that determines how fast your applications runs applications and completes processes, like rendering a model in Autodesk's Maya or exporting an image in Adobe's Photoshop). Any subsequent time you open your project the process will be much faster.

Before we begin the workshop there is another important step we need to take. This step will sound very unintuitive, but necessary if you want to save any work you want to save in your Unity project. First you will need to close the Unity Editor by selecting the ```Quit``` option in the menu system. At this point you will be prompted to ```Keep project?```. To save your project select ```Keep Project``` and then decide where to save your project and click ```Save```. You may want to give your project a name so it is easy to find. Now, go back into the Unity Hub and go to the ```Projects``` tab and click ```Add```. Remember where you saved your project and click ```Open``` on your project folder. The project will then appear in the ```Projects``` tab within the Hub. You will notice that it provides you with the ```Project Name```, ```Unity Version```, ```Target Platform```, and ```Last Modified```. This feature essentially lets you know how you are managing your project and if there are any technical issues (i.e., you are running the corresponding version of the Editor with the project).

Now that you have save your project and connected it to the Unity Hub, you can now reopen your project and get started with the workshop!

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



