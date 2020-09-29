---
layout: page
title: Instagram-Scraper for Instagram Data
permalink: /workshops/twarc/
---
## Table of Contents

1. [About](#about)  
2. [Resources](#resources)  
  2.1 [Ethics](#ethics)  
  2.2 [Copyright](#copyright)  
3. [Setup](#setup)  
  3.1 [Linux Instructions](#linux)  
  3.2 [Windows Instructions](#windows)  
  3.3 [OS X Instructions](#osx)  
4. [Workshop](#workshop)  
  4.1 [Create Research Persona](#persona)  
  4.2 [Warm-Up](#warmup)  
  4.3 [Gather User Account Data](#exercise1)  
  4.4 [Gather Hashtag Data](#exercise2)  
  4.5 [Gather Location Data](#exercise3)  
5. [Final Thoughts](#final)

Workshop by [Chris Young](mailto:christopher.young@utoronto.ca)

## 1. About <a name="about"></a>

instagram-scraper is a command-line application written in Python that scrapes and downloads an instagram user's photos, videos, and metadata. instagram-scraper can be used to gather Instagram data from user accounts, hashtags, and locations including metadata, like user comments. Photos and videos are stored in your folder and metadata are stored as line-oriented JSON.

As you can imagine, instagram-scraper can be quite useful if you are interested in building an archive of Instagram data, which could include posts, comments, geolocation, and numerous metadata that cannot easily be scraped via Instagram’s user interface. However, while instagram-scraper can retrieve almost anything from Instagram it is important to read Instagram's [Terms of Use](https://www.facebook.com/help/instagram/1188470931252371). Specifically, the Terms of Use state, "We prohibit crawling, scraping, caching or otherwise accessing any content on the Service via automated means, including but not limited to, user profiles and photos..." As such, the instagram-scraper along with any automated tools should be used with caution when gathering Instagram data for research purposes.

In the documentation provided in this workshop, we only cover how you can setup instagram-scraper and gather Instagram data, such as user's photos, videos, and metadata. If you are in doubt about whether your research project meets ethics requirements and fair use of copyrighted works you can consult your instituitonal research office and scholarly communications officer. If you do not have access to such resources take a look at our Ethics and Copyright sections below for more information.

## 2. Resources <a name="resources"></a>

There are some fantastic resources out there to learn how to use instagram-scraper for gathering an archive of Instagram data in digital research. The most important resource to consult is the [instagram-scraper GitHub page](https://github.com/arc298/instagram-scraper) by Richard Arcega. The project page includes all the relevant commands for how to use instagram-scraper as well as any updates to the command line tool.

### 2.1 Ethics <a name="ethics"></a>
Digital research ethics of online material is a constantly moving fence. Most post-secondary institutions have Research Offices with policies on the use of human data, which can include data posted on social media posted behind password protested accounts. Check in with your research office if the data you intend to collect from online sources was created by humans to learn more about ethical decision-making of online data. For faculty, staff, and students at UTM, you can contact our Research Office to learn more about [Ethics in Research](https://www.utm.utoronto.ca/vp-research/information-researchers/ethics-research).

A good first resource to consult if you are wantin a quick-and-fast answer to your ethical decision-making of online data is the [Association of Internet Research's](https://aoir.org/) recommendations from its [Ethical Working Committee](https://aoir.org/ethics/). The Committee is constantly updating its documentation and its current recommendations along with a condensed information chart are a good starting point to determine your research ethics:

[Ethical Decision-Making and Internet Research](https://aoir.org/reports/ethics3.pdf)  
[Chart](https://aoir.org/wp-content/uploads/2017/01/aoir_ethics_graphic_2016.pdf)

### 2.2 Copyright <a name="copyright"></a>
Copyright has an impact on digital research activities, including the copying of files from the internet using wget. Most post-secondary institutions have Scholarly Communication and Copyright offices with copyright guideliens on fair dealing. Check in with your scholarly communication and copyright office if you are sure your data collection falls under fair dealing. For faculty, staff, and students at UTM, you can contact our [Scholarly Communication Librarian](https://utm.library.utoronto.ca/scholarly-communications) to learn more about copyright fair dealing. The University has also put together a number of resources you can consult if you need a quick-and-fast answer:

[Copyright Fair Dealing Guidelines](https://provost.utoronto.ca//wp-content/uploads/sites/155/2018/06/Copyright-Guidelines.pdf)  
[Copyright Basics](https://onesearch.library.utoronto.ca/sites/default/files/copyright/basicsfaqs_092018.pdf)  
[Copyright Road Map](https://onesearch.library.utoronto.ca/sites/default/files/copyright/utl_copyrightroadmap.pdf)

Some other useful resources to consult on copyright fair dealing include:

Canadian Association of Research Libraries' [fair dealing documentation](https://fair-dealing.ca/what-is-fair-dealing/)  
The Writers Union of Canada's [fair dealing documentation](https://www.writersunion.ca/what-and-isn-t-fair-dealing)  
Council of Ministers of Education's [fair dealing decision tool](http://www.fairdealingdecisiontool.ca/DecisionTool/)

Note, these copyright resources only pertain to the [*Copyright Act*](https://laws-lois.justice.gc.ca/eng/acts/C-42/) for fair dealing in Canada and does not cover copyright in other jurisdictions. For international researchers please consult your own scholarly communication and copyright offices and resources on fair use or fair dealing of copyrighted works in digital research.

## 3. Setup <a name="setup"></a>
Before we begin with the workshop component of how to use instagram-scraper for digital research there is some preliminary setup we have to complete on your computer. Since instagram-scraper is used through the command line, we have to install packages onto your computer for it work. Depending on which operating system you use, setup can be straightforward or the most time consuming aspect of learning how to use instagram-scraper. Below are installation instructions for Linux, Windows, and OS X users which all require the installation of Python and the pacakge manager Pip to install Python pacakges, like instagram-scraper. Once instagram-scraper is installed on each system, the instructions will be the same for every user participating in the workshop.

### 3.1 Linux Instructions <a name="linux"></a>
Ubuntu ships with Python 3, as the default Python installation. Complete the following steps to install pip (pip3) for Python 3. Start by updating the package list using the following command in the command line:

```sudo apt update```

Once the package list is updated, use the following command to install pip for Python 3:

```sudo apt install python3-pip```

When prompted to select ```yes``` or to type ```y```, please do so to install the package. The command above will also install the dependencies required for building Python modules.

Once the installation is complete, verify the installation by checking the pip version:

```pip3 --version```

The output version my vary, but it will look something like this:

```pip 20.2.3 from [YOUR DIRECTORY] (python 3.8)```

Now that pip is installed, we can use it to install twarc. Type and enter the following command into the command line:

```pip3 install instagram-scraper```

It will proceed to download the most recent version of instagram-scraper, which us version 1.9.0. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```instagram-scraper```

If twarc has installed, you will see dozens of lines of commands that end with the following statement:

```ValueError: Must provide username(s) OR a file containing a list of username(s) OR pass --followings-input```

This means instagram-scraper has installed and you need to use an argument after ```instagram-scraper```. If instagram-scraper is not installed on your system it will respond with:

```$ command not found.```

At this point, however, instagram-scraper should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing pip.

### 3.2 Windows Instructions <a name="windows"></a>
The easiest way for Windows machines is to download and install Python. To do so, download the latest version of Python from the [python.org website](https://www.python.org/downloads/)(as of writing it is version 3.8.5). When you have downloaded the Python package you will need to open it and install it. Before you click through the agreement, make sure you select ```Add to PATH``` in the options window. This is critical as it will add your installation of Python 3.8.5 to your PATH for use in the command prompt. 

Once the installation is complete, verify the installation by checking the pip version:

```pip3 --version```

The output version my vary, but it will look something like this:

```pip 20.2.3 from [YOUR DIRECTORY] (python 3.8)```

Now that pip is installed, we can use it to install twarc. Type and enter the following command into the command line:

```pip3 install instagram-scraper```

It will proceed to download the most recent version of instagram-scraper, which us version 1.9.0. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```instagram-scraper```

If twarc has installed, you will see dozens of lines of commands that end with the following statement:

```ValueError: Must provide username(s) OR a file containing a list of username(s) OR pass --followings-input```

This means instagram-scraper has installed and you need to use an argument after ```instagram-scraper```. If instagram-scraper is not installed on your system it will respond with:

```$ command not found.```

At this point, however, instagram-scraper should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing pip.

### 3.3 OS X Instructions <a name="osx"></a>
The easiest way for Windows machines is to download and install Python. To do so, download the latest version of Python from the [python.org website](https://www.python.org/downloads/)(as of writing it is version 3.8.5). When you have downloaded the Python package you will need to open it and install it. After you click through the installation process you will need to verify the Python certifications and update your terminal shell. In the finder window for Python 3.8 click on the "Install Certificates.command" to verify Python packages. This will open up the Terminal to update the Python certificates. Wait until you read the message ```[Process completed]```. Close the terminal, then click on "Update Shell Profile.command" to update the terminal. This updates the Terminal in your bin directory so you can access python from the terminal. Wait until you read the message ```[Process completed]```. Close the terminal.

Open a new terminal and verify the installation is complete by checking the pip version:

```pip3 --version```

The output version my vary, but it will look something like this:

```pip 20.2.3 from [YOUR DIRECTORY] (python 3.8)```

Now that pip is installed, we can use it to install twarc. Type and enter the following command into the command line:

```pip3 install instagram-scraper```

It will proceed to download the most recent version of instagram-scraper, which us version 1.9.0. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```instagram-scraper```

If twarc has installed, you will see dozens of lines of commands that end with the following statement:

```ValueError: Must provide username(s) OR a file containing a list of username(s) OR pass --followings-input```

This means instagram-scraper has installed and you need to use an argument after ```instagram-scraper```. If instagram-scraper is not installed on your system it will respond with:

```$ command not found.```

At this point, however, instagram-scraper should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing pip.

## 4. Workshop <a name="workshop"></a>

Does your research require you to build an archive of Instagram data? In this workshop attendees will learn how to gather Instagram data with the instagram-scraper program in your command line interface without going through the tedious process of manually downloading Instagram posts. Participants will also be guided through the process of cleaning up Instagram data once it’s downloaded.

For this workshop we are going to build an archive of Instagram data using the command line tool instagram-scraper. We are going to walk through a few exercises using instagram-scraper in your operating system’s command line interface: terminal for Linux and OS X and command prompt for Windows. If you have followed the setup instructions to install instagram-scraper on your Linux, Windows, or OS X machines then you are ready to begin the workshop.

### 4.1 Create Research Profile <a name="persona"></a>


### 4.2 Warm Up <a name="warmup"></a>

All of the commands in instagram-scraper use the following logic when being used:

```instagram-scraper [text] [--options]```

instagram-scraper has one query for gathering Instagram data: ```text```. The text query allows you to retrieve all post data pertaining to a user account, hashtag, or location. The query retrieves all data currently associated with an account, hashtag, or location as long as it is not a private account. If an account is set to private that user's Instagram data will be unavailable. The only exception is if you have an account where you are an approved follower and you include the ```[username]``` and ```[password]``` information for your research persona which is an approved followed of the user account you intend to gather Instagram data from. 

As such, if you are retrieving data from a private user account where you are an approved follower, the logic of instagram-scraper is as follows:

```instagram-scraper [text] -u [username] -p [password] [--options]```

When customizing your search query with options, you can use filters, limitations, and include specific metadata. Some of the filters include gathering queries by geolocation and mediatypes. Some of the limitations include a maximum number of posts to gather and the latest posts since the previous scrape command. And some of the specific metadata can include comments and profile metadata.

### 4.3 Gather User Account Data <a name="exercise1"></a>


### 4.4 Gather Hashtag Data <a name="exercise2"></a>


### 4.5 Gather Location Data <a name="exercise3"></a>


## 5. Final Thoughts <a name="final"></a>

As you become increasingly comfortable with the command line, you will find instagram-scraper a helpful addition to your digital research toolkit. If there is a selection of Instagram data that you want to download for text mining and analysis, a quick instagram-scraper command will be quicker than scraping the links manually. While this workshop focuses on a few of the commands, a fuller list with quick examples can be found at the [instagram-scraper GitHub project](https://github.com/arc298/instagram-scraper).
