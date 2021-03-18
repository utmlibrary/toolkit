---
layout: page
title: Gather Twitter Data with twarc
permalink: /workshops/twarc/
---
## Table of Contents

1. [About](#about)  
2. [Resources](#resources)  
  2.1 [Tutorials](#tutorials)  
  2.2 [Ethics](#ethics)  
  2.3 [Copyright](#copyright)  
3. [Setup](#setup)  
  3.1 [Linux Instructions](#linux)  
  3.2 [Windows Instructions](#windows)  
  3.3 [OS X Instructions](#osx)  
4. [Workshop](#workshop)  
  4.1 [Configuration](#configuration)  
  4.2 [Warm-Up](#warmup)  
  4.3 [Gather by Term and Hashtag](#exercise1)  
  4.4 [Gather by Twitter Account](#exercise2)  
5. [Final Thoughts](#final)

Workshop by [Chris Young](mailto:christopher.young@utoronto.ca)  
Last updated November 10, 2020

## 1. About <a name="about"></a>

twarc is a command line tool and Python library for archiving Twitter JSON data. Each tweet is represented as a JSON object that is exactly what was returned from the Twitter API. Tweets are stored as line-oriented JSON. Twarc will handle Twitter API's rate limits for you. In addition to letting you collect tweets Twarc can also help you collect users, trends and hydrate tweet ids. twarc was developed as part of the Documenting the Now project which was funded by the Mellon Foundation.

As you can imagine, twarc can be quite useful if you are interested in building an archive of Twitter data, which could include tweets, comments, trends, geolocation, and numerous metadata that cannot be scraped via Twitter's user interface. However, while twarc can retrieve almost anything from Twitter it is important to read Twitter's [Developer Agreement and Policy](https://developer.twitter.com/en/developer-terms/agreement-and-policy) and list of [restricted use cases](https://developer.twitter.com/en/developer-terms/more-on-restricted-use-cases). 

In the documentation provided in this workshop, we only cover how you can setup twarc and scrape Twitter data, such as trends. If you are in doubt about whether your research project meets ethics requirements and fair use of copyrighted works you can consult your instituitonal research office and scholarly communications officer. If you do not have access to such resources take a look at our [Ethics](#ethics) section below for more information.

## 2. Resources <a name="resources"></a>

There are some fantastic resources out there to learn how to use twarc for gathering an archive of Twitter data in digital research. The most important resource to consult is the [twarc GitHub page](https://github.com/DocNow/twarc) by the Gathering the Now project. The project page includes all the relevant commands for how to use twarc as well as any updates to the command line tool.

### 2.1 Tutorials <a name="tutorials"></a>

There are also some useful tutorials on how to use twarc by several libraries with a focus on digital research: 

[University of Virginia Library's social media toolkit](http://digitalcollecting.lib.virginia.edu/toolkit/docs/social-media/)  
[Temple University Library's webscraping guide](https://guides.temple.edu/c.php?g=123755&p=6097990)  
[Penn State University Library's Twitter research guide](https://guides.libraries.psu.edu/c.php?g=796631&p=5698003)  
[Carleton University Gould Library's Twitter API tutorial](http://gouldguides.carleton.edu/dataknowledgebase/twitterapi)  
[McGill University Library's text data mining guide](https://libraryguides.mcgill.ca/c.php?g=702813&p=5064861)

### 2.2 Ethics <a name="ethics"></a>
Digital research ethics of online material is a constantly moving fence. Most post-secondary institutions have Research Offices with policies on the use of human data, which can include data posted on social media posted behind password protected accounts. Check in with your research office if the data you intend to collect from online sources was created by humans to learn more about ethical decision-making of online data. For faculty, staff, and students at UTM, you can contact our Research Office to learn more about [Ethics in Research](https://www.utm.utoronto.ca/vp-research/information-researchers/ethics-research).

A good first resource to consult if you want a quick-and-fast answer to your ethical decision-making of online data is the [Association of Internet Research's](https://aoir.org/) recommendations from its [Ethical Working Committee](https://aoir.org/ethics/). The Committee is constantly updating its documentation and its current recommendations along with a condensed information chart are a good starting point to determine your research ethics:

[Ethical Decision-Making and Internet Research](https://aoir.org/reports/ethics3.pdf)  
[Chart for Internet Researcher Ethics](https://aoir.org/wp-content/uploads/2017/01/aoir_ethics_graphic_2016.pdf)

### 2.3 Copyright <a name="copyright"></a>
Copyright has an impact on digital research activities, including the copying of files from the internet using twarc. Most post-secondary institutions have Scholarly Communication and Copyright offices with copyright guidelines on fair dealing. Check in with your scholarly communication and copyright office if you are sure your data collection falls under fair dealing. For faculty, staff, and students at UTM, you can contact our [Scholarly Communication Librarian](https://utm.library.utoronto.ca/scholarly-communications) to learn more about copyright fair dealing. The University has also put together a number of resources you can consult if you need a quick-and-fast answer:

[Copyright Fair Dealing Guidelines](https://provost.utoronto.ca//wp-content/uploads/sites/155/2018/06/Copyright-Guidelines.pdf)  
[Copyright Basics](https://onesearch.library.utoronto.ca/sites/default/files/copyright/basicsfaqs_092018.pdf)  
[Copyright Road Map](https://onesearch.library.utoronto.ca/sites/default/files/copyright/utl_copyrightroadmap.pdf)

Some other useful resources to consult on copyright fair dealing include:

Canadian Association of Research Libraries' [fair dealing documentation](https://fair-dealing.ca/what-is-fair-dealing/)  
The Writers Union of Canada's [fair dealing documentation](https://www.writersunion.ca/what-and-isn-t-fair-dealing)  
Council of Ministers of Education's [fair dealing decision tool](http://www.fairdealingdecisiontool.ca/DecisionTool/)

Note, these copyright resources only pertain to the [*Copyright Act*](https://laws-lois.justice.gc.ca/eng/acts/C-42/) for fair dealing in Canada and does not cover copyright in other jurisdictions. For international researchers please consult your own scholarly communication and copyright offices and resources on fair use or fair dealing of copyrighted works in digital research.

## 3. Setup <a name="setup"></a>

Before we start the workshop component of how to build an archive of Twitter data with the command line tool twarc, there is some preliminary setup we have to complete on your computer and with Twitter. Since twarc is used through the command line, we have to install packages onto your computer for it work. Depending on which operating system you use, setup can be straightforward or the most time consuming aspect of learning how to use twarc. Below are installation instructions for Linux, Windows, and OS X users. Once twarc is installed on each system, the instructions will be the same for every user participating in the workshop.

Before we install twarc we need to register an application at [developer.twitter.com](https://developer.twitter.com/en/apps). To do this you will need a Twitter account and then register as a developer. Once these steps are completed you can register an application by clicking the ```create an app``` icon. The app is required to generate the API keys we need to interact with twarc to build an archive of data. To create the app there are a series of required fields which need to be filled out, including: App name, Application Description, Website URL, and Tell us how this app will be used. There is no magic recipe to filling out the form. However, it is important that you emphasize the app is for research purposes only as you are not using the app for commercial or government purposes. I used the following information when I created the application:

```App name: twarc research profile 1```  
```Application description: To be used to gather research data in the twarc command line tool.```  
```Website URL: [enter your url]```  
```Tell us how this app will be used: The app will be used to communicate with twarc to archive tweets for analysis in research projects on social media.```  

When prompted, be sure to read the [Developer Agreement and Policy](https://developer.twitter.com/en/developer-terms/agreement-and-policy) and Twitter's list of [restricted use cases](https://developer.twitter.com/en/developer-terms/more-on-restricted-use-cases).

You may receive a follow up from Twitter about your app, but it is a relatively straightforward process you can complete in a few minutes. You may need to wait a day or two to receive your confirmation, which is why it is important to complete this step first.

### 3.1 Linux Instructions <a name="linux"></a>
Ubuntu ships with Python 3, as the default Python installation. Complete the following steps to install pip (pip3) for Python 3. Start by updating the package list using the following command in the command line:

```sudo apt update```

Once the package list is updated, use the following command to install pip for Python 3:

```sudo apt install python3-pip```

When prompted to select ```yes``` or to type ```y```, please do so to install the package. The command above will also install the dependencies required for building Python modules.

Once the installation is complete, verify the installation by checking the pip version:

```pip3 --version```

The output version my vary, but it will look something like this:

```pip 9.0.1. from /usr/lib/python3/dist-packages (python 3.6)```

Now that pip is installed, we can use it to install twarc. Type and enter the following command into the command line:

```pip3 install twarc```

It will proceed to download the most recent version of twarc, which is twarc 1.10. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```twarc```

If twarc has installed, you will see almost a dozen lines of commands that end with the following statement:

```twarc: error: the following arguments are required: command```

This means twarc has installed and you need to use an argument after twarc. If twarc is not installed on your system it will respond with:

```$ command not found.```

At this point, however, twarc should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing pip.

### 3.2 Windows Instructions <a name="windows"></a>
The easiest way for Windows machines is to download and install Python. To do so, download the latest version of Python from the [python.org website](https://www.python.org/downloads/)(as of writing it is version 3.8.5). When you have downloaded the Python package you will need to open it and install it. Before you click through the agreement, make sure you select ```Add to PATH``` in the options window. This is critical as it will add your installation of Python 3.8.5 to your PATH for use in the command prompt. 

Once the installation is complete, verify the installation by checking the pip version:

```pip3 --version```

The output version my vary, but it will look something like this:

```pip 20.2.3 from [YOUR DIRECTORY] (python 3.8)```

Now that pip is installed, we can use it to install twarc. Type and enter the following command into the command line:

```pip3 install twarc```

It will proceed to download the most recent version of twarc, which is twarc 1.10. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```twarc```

If twarc has installed, you will see almost a dozen lines of commands that end with the following statement:

```twarc: error: the following arguments are required: command```

This means twarc has installed and you need to use an argument after twarc. If twarc is not installed on your system it will respond with:

```$ command not found.```

At this point, however, twarc should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing pip.

### 3.3 OS X Instructions <a name="osx"></a>
The easiest way for Windows machines is to download and install Python. To do so, download the latest version of Python from the [python.org website](https://www.python.org/downloads/)(as of writing it is version 3.8.5). When you have downloaded the Python package you will need to open it and install it. After you click through the installation process you will need to verify the Python certifications and update your terminal shell. In the finder window for Python 3.8 click on the "Install Certificates.command" to verify Python packages. This will open up the Terminal to update the Python certificates. Wait until you read the message ```[Process completed]```. Close the terminal, then click on "Update Shell Profile.command" to update the terminal. This updates the Terminal in your bin directory so you can access python from the terminal. Wait until you read the message ```[Process completed]```. Close the terminal.

Open a new terminal and verify the installation is complete by checking the pip version:

```pip3 --version```

The output version my vary, but it will look something like this:

```pip 20.2.3 from [YOUR DIRECTORY] (python 3.8)```

Now that pip is installed, we can use it to install instagram-scraper. Type and enter the following command into the command line:

```pip3 install twarc```

It will proceed to download the most recent version of twarc, which is twarc 1.10. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```twarc```

If twarc has installed, you will see almost a dozen lines of commands that end with the following statement:

```twarc: error: the following arguments are required: command```

This means twarc has installed and you need to use an argument after twarc. If twarc is not installed on your system it will respond with:

```$ command not found.```

At this point, however, twarc should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing Homebrew.

## 4. Workshop <a name="workshop"></a>

Does your research require you to build an archive of Twitter data? In this workshop attendees will learn how to scrape tweets with the TWARC program in your command line interface without going through the tedious process of manually downloading tweets. Participants will also be guided through the process of cleaning up Twitter data once it’s downloaded.

For this workshop we are going to build an archive of Twitter data using the command line tool twarc. We are going to walk through a few exercises using twarc in your operating system’s command line interface: terminal for Linux and OS X and Ubuntu for Windows. If you have followed the setup instructions to install twarc on your Linux, Windows, or OS X machines then you are ready to begin the workshop.

### 4.1 Configuration <a name="configuration"></a>
At this point you should have twarc installed and have created your app with Twitter. Now, we need to configure twarc with your app credentials. On the developer.twitter.com interface you will be able to view your app. When you open the app, you will need to view the ```keys and tokens```. Note, the ```Consumer API Keys```, whih includes a ```API key``` and ```API secret key```.

Returning to the command line, you are going to need to tell twarc about your application API keys and grant access to your Twitter account. Type and enter in the following command:

```twarc configure```

When prompted, you will be asked to enter your ```consumer key```. Copy and paste the ```API key``` from your app into the command line and hit enter.

You will then be prompted to enter your ```consumer secret```. Copy and paste the ```API secret key``` from your app into the command line and hit enter.

You will then be asked to authorize the application by entering a pin which will be provided by a URL printed in the command line. Go to the URL and type the pin into the command line. If all has gone well, you should receive a message stating ```Happy twarcing!```.

### 4.2 Warm Up <a name="warmup"></a>
All of the commands in twarc use the following logic when being used:

```twarc [query] [text] [--filter] [text] > [file output]```

Twarc has two main queries for gather tweets: ```search``` and ```filter```. The search query retrieves all tweets sent out over the past 7 days that meet your command's instructions. Twitter's search API imposes a 7 day cap which is why you cannot go further back in time. The filter query retrieves all tweets sent out as they happen. This means when you start the command you will need to leave it running on your computer until you have finished your study.

For example, you could use the following command to gather tweets on COVID-19 from accounts tweeting in Toronto as they happen, where the query is ```filter``` and the filter is ```geocode```:

```twarc filter covid19 --geocode 43.653226,-79.383184,10mi > coronavirustweetsastheyhappen.jsonl```

If you want to gather tweets for a few days, a month, or a year, you let the command run in the terminal for the period of time you require. If you want to gather tweets from the previous week, can can swap out the ```filter``` query for ```search```, so you're command looks like this:

```twarc search covid19 --geocode 43.653226,-79.383184,10mi > covid19tweetspreviousweek.jsonl```

A good first exercise though to warm up with if you have never used twarc before is the ```sample``` query. The sample command listens to Twitter's [statuses/sample](https://developer.twitter.com/en/docs/tutorials/consuming-streaming-data) API for a "random" sample of recent public statuses. To use the command, type and enter in the following command:

```twarc sample > sampletweets.jsonl```

You only need to run the command for a few seconds so hit ```control``` or ```ctrl``` and ```c``` to stop the command. The sample command gathers tweets from all over the world, so a few seconds generates hundreds of tweets (if not thousands!).

To view the jsonl file you've created you can open the file with a text editor, such as [BBEdit](https://apps.apple.com/us/app/bbedit/id404009241?mt=12) on OSX or [notepad ++](https://notepad-plus-plus.org/downloads/) on Windows.

### 4.3 Gather by Term and Hashtag <a name="exercise1"></a>
Let's say you want to gather Twitter data on users around a given topic that is encapsulated by a hashtage or a series of terms. As noted in the warm up section, you can gather tweets as they happen using the ```filter``` query and the past week's tweets using the ```search```.

For this exercise, we want to gather tweets on COVID-19, which are differentiated here for search and filter:

```twarc search covid, covid19,coronavirus,corona virus > covid19search.jsonl```  
or  
```twarc filter covid,covid19,coronavirus,corona virus > coronavirussearch.jsonl```

Note, we are using four variants of COVID-19 to capture the term as it's been used on Twitter.

Using either of these commands will gather all tweets on Twitter using the term. However, we will want to delimit this information either by geolocation and/or language.

As noted in the warm up section, you could use ```geocode``` to limit tweets by a geolocation, like Toronto:

```twarc filter covid --geocode 43.653226,-79.383184,10mi > covid19tweetsastheyhappen.jsonl```  
or  
```twarc search covid --geocode 43.653226,-79.383184,10mi > covid19tweetspreviousweek.jsonl```  

You can also use language as Twitter attempts to code the language of a Tweet (note, this is not 100% accurate). You can limite your search to a particular language using an [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) code:

```twarc filter covid --geocode 45.501689,-73.567256,10mi --lang fr > coronavirustweetsastheyhappen.jsonl```  
or  
```twarc search covid --geocode 45.501689,-73.567256,10mi --lang fr > coronavirustweetspreviousweek.jsonl```  

As you can see from this example, we differentiated the search and filter commands by the location of Montreal and the language French. This type of filter can be useful when you're trying to get a sense of how a specific community in a geolocation tweets about a topic.

### 4.4 Gather by Twitter Account <a name="exercise2"></a>
Another strategy to gather Twitter data is by selecting specific Twitter accounts. As noted in the warm-up section, you can gather tweets as they happen using the ```filter``` query and the past week's tweets using the ```search```.

For this exercise, we want to gather tweets sent out by specific organizations on COVID-19, which are differentiated here for search and filter. Note, we use the ```follow``` command followed by the userid of the Twitter account. To get the userid of an account, [GetTwitterID](http://gettwitterid.com/) can generate a userid using the twitter handle as input. In the case of this example, we are gathering all tweets from the World Health Organization on the coronavirus:

```twarc filter covid --follow 14499829 > covid19tweetsbyorganizationlive.jsonl```  
or  
```twarc search covid --follow 14499829 > covid19tweetsbyorganizationpast```

As you can see, it will only scrape tweets sent by this organization when they tweet the term COVID. Some researchers may want to develop a list of accounts they want to follow on a topic and these can added to the ```follow``` function by adding a comma (```,```) with no spaces after each each userid.

## 5. Final Thoughts <a name="final"></a>
As you become increasingly comfortable with the command line, you will find twarc a helpful addition to your digital research toolkit. If there is a selection of twitter data that you want to download for text mining and analysis, a quick twarc command will be quicker than scraping the links manually. While this workshop focuses on a few of the commands, a fuller list with quick examples can be found at the [twarc GitHub project](https://github.com/DocNow/twarc).

Here is a [download link](files/scilit2020.jsonl) to an jsonl file example of a twarc filter search for tweets on Science Literacy Week in 2020 (#scilit). You can open and view the file with text editor, such as [BBEdit](https://apps.apple.com/us/app/bbedit/id404009241?mt=12) on OSX or [notepad++](https://notepad-plus-plus.org/downloads/) on Windows.
