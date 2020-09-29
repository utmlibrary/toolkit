---
layout: page
title: Gather Webpage Data with wget
permalink: /workshops/wget/
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
4. [Workshops](#workshops)  
    4.1 [Warm Up](#warmup)  
    4.2 [Retrieve a Webpage or File](#exercise1)  
    4.3 [Retrieve Multiple Files from a Website](#exercise2)  
    4.4 [Mirror a Website](#exercise3)
5. [Final Thoughts](#final)

Workshop by [Chris Young](mailto:christopher.young@utoronto.ca)

## 1. About <a name="about"></a>

Wget is a free command line utility for non-interactive downloads of files from the web to retrieve online material. It supports HTTP, HTTPS, and FTP protocols, as well as retrieval through HTTP procies. Wget can also follow links in HTML, XHTML, and CSS pages, to create local versions of remote websites, fully recreating the directory structure of the original site. This means researchers can use wget to gather copies of online digital content for their research projects.

As you can imagine, wget can be quite useful if you are interested in building an archive of online data from websites, which could include documents, videos, images, and audio files. However, while wget can retrieve almost anything online it is important to read the end-user license agreements (EULAs) of websites you download from and know what falls under fair use when you download copies of files. In the documentation provided in this workshop, we only cover how you can download online digital files from public websites, such as Government Archives. Downloading data from social media accounts, digital game sites, and other login platform-based services is not covered in this workshop. If you are in doubt about whether your research project meets ethics requirements and fair use of copyrighted works you can consult your instituitonal research office and scholarly communications officer. If you do not have access to such resources take a look at our Resources page for more information.

## 2. Resources <a name="resources"></a>

There are some fantastic resources out there to learn how to use wget for a variety of purposes beyond digital research. The most important resource to consult is the [Wget Manual](https://www.gnu.org/software/wget/manual/wget.html) by the Free Software Foundation, the developers of the GNU operating system and wget. The manual includes all the relevant commands for how to use wget.

### 2.1 Tutorials <a name="tutorials"></a>

There are also some useful tutorials with a focus on digital research. [The Programming Historian](https://programminghistorian.org/) has two workshops on wget with a focus on creating a web archive for digital research, which most of this site's documentation is derived from:

[Automated Downloading with Wget](https://programminghistorian.org/en/lessons/automated-downloading-with-wget)  
[Applied Archival Downloading with Wget](https://programminghistorian.org/en/lessons/applied-archival-downloading-with-wget)

### 2.2 Ethics <a name="ethics"></a>
Digital research ethics of online material is a constantly moving fence. Most post-secondary institutions have Research Offices with policies on the use of human data, which can include data posted on social media posted behind password protested accounts. Check in with your research office if the data you intend to collect from online sources was created by humans to learn more about ethical decision-making of online data. For faculty, staff, and students at UTM, you can contact our Research Office to learn more about [Ethics in Research](https://www.utm.utoronto.ca/vp-research/information-researchers/ethics-research).

A good first resource to consult if you are wantin a quick-and-fast answer to your ethical decision-making of online data is the [Association of Internet Research's](https://aoir.org/) recommendations from its [Ethical Working Committee](https://aoir.org/ethics/). The Committee is constantly updating its documentation and its current recommendations along with a condensed information chart are a good starting point to determine your research ethics:

[Ethical Decision-Making and Internet Research](https://aoir.org/reports/ethics3.pdf)  
[Chart for Internet Researcher Ethics](https://aoir.org/wp-content/uploads/2017/01/aoir_ethics_graphic_2016.pdf)

### 2.3 Copyright <a name="copyright"></a>
Copyright has an impact on digital research activities, including the copying of files from the internet using wget. Most post-secondary institutions have Scholarly Communication and Copyright offices with copyright guidelines on fair dealing. Check in with your scholarly communication and copyright office if you are not sure your data collection falls under fair dealing. For faculty, staff, and students at UTM, you can contact our [Scholarly Communication Librarian](https://utm.library.utoronto.ca/scholarly-communications) to learn more about copyright fair dealing. The University has also put together a number of resources you can consult if you need a quick-and-fast answer:

[Copyright Fair Dealing Guidelines](https://provost.utoronto.ca//wp-content/uploads/sites/155/2018/06/Copyright-Guidelines.pdf)  
[Copyright Basics](https://onesearch.library.utoronto.ca/sites/default/files/copyright/basicsfaqs_092018.pdf)  
[Copyright Road Map](https://onesearch.library.utoronto.ca/sites/default/files/copyright/utl_copyrightroadmap_february2020update.pdf)

Some other useful resources to consult on copyright fair dealing include:

Canadian Association of Research Libraries' [fair dealing documentation](https://fair-dealing.ca/what-is-fair-dealing/)  
The Writers Union of Canada's [fair dealing documentation](https://www.writersunion.ca/what-and-isn-t-fair-dealing)  
Council of Ministers of Education's [fair dealing decision tool](http://www.fairdealingdecisiontool.ca/DecisionTool/)

Note, these copyright resources only pertain to the [*Copyright Act*](https://laws-lois.justice.gc.ca/eng/acts/C-42/) for fair dealing in Canada and does not cover copyright in other jurisdictions. For international researchers please consult your own scholarly communication and copyright offices and resources on fair use or fair dealing of copyrighted works in digital research.

## 3. Setup <a name="setup"></a>

Before we begin with the workshop component of how to use Wget for digital research there is some preliminary setup we have to complete on your computer. Since wget is used through the command line, we have to install packages onto your computer for it work. Depending on which operating system you use, setup can be straightforward or the most time consuming aspect of learning how to use wget. Below are installation instructions for Linux, Windows, and OS X users. Once wget is installed on each system, the instructions will be the same for every user participating in the workshop.

### 3.1 Linux Instructions <a name="linux"></a>
If you are using Linux operating system, then you should already have wget installed--hooray! To check if wget is already installed on your Linux system, open up your command line. In the command prompt, type ```'wget'``` and press enter. If wget is already installed the system will respond with: 


```$ wget: missing URL```  
```Usage: wget [OPTION]... [URL]...```  
```Try 'wget --help' for more options.```

If wget is not installed on your system it will respond with:

```$ command not found.```

If you receive this error message, follow the OS X instructions below.

### 3.2 Windows Instructions <a name="windows"></a>
The easiest way is to download a working version. To do so, visit [this website](https://eternallybored.org/misc/wget/) and, download ```wget.exe``` (as of writing it is version 1.20, and you should download the 32-bit binary). The file is the second link in the 32-bit binary column, entitled just ```wget.exe```.

If you place ```wget.exe``` in your ```C:\Windows``` directory, you can then use wget from anywhere on your computer. This will make your life easier as you will not have to worry about always running wget from only one place on your system. If it is in this directory, Windows will know that the command can be used anywhere in your terminal window.

Now that Wget is installed, you can open the Command Prompt terminal window. You can access the Command Prompt by typing ```command prompt``` in the search bar by Start and opening the application. In the Command Prompt, type ```wget``` and press enter. If wget is already installed the system will respond with:

```$ wget: missing URL```  
```Usage: wget [OPTION]... [URL]...```  
```Try 'wget --help' for more options.```

If wget is not installed on your system it will respond with:

```$ command not found.```

If you receive this error message, check through the instructions above to make sure you didn't miss a step.

### 3.3 OS X Instructions <a name="osx"></a>
On OS X, there are two ways to get wget and install it. The easiest is to install a package manager and use it to automatically install wget. There is a second method, discussed below, that involves compiling it.

Both, however, require that you install Apple’s ‘Command Line Tools’ to use properly. This requires downloading XCode. If you have the ‘App Store’, you should be able to just download XCode via this link.  If not, the following instructions will work.

To download this, go to the Apple Developer website, register as a developer, and then in the downloads for Apple developers section you will need to find the correct version. If you are on the most recent version, Lion as of July 2012, you can use the main link. If not, you will need to click on the link: “Looking for additional developer tools? View Downloads.”

After logging in with your free developer credentials, you will see a long list. Type xcode in the search bar and find a version that is compatible with your operating system version. This may take some clicking around to find the right version for you. For example, Xcode 3.2 is the version for OS X 10.6 Snow Leopard, 3.0 is the version for OS X 10.5 Leopard, etc.

It is a big download, and will take some time. Once you have the file, install it.

You will need to install the ‘Command Line Tools’ kit in XCode. Open up the ‘Preferences’ tab, click on ‘Downloads,’ and then click ‘Install’ next to Command Line Tools. We are now ready to install a package manager.

The easiest package manager to install is Homebrew. Go to https://brew.sh and review the instructions. There are many important commands, like wget, that are not included by default in OS X. This program facilitates the downloading and installation of all required files.

To install Homebrew, open up your terminal window and type the following:

```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```

This uses the ruby programming language, built into OS X, to install Homebrew. To see if the installation worked, type the following into your terminal window:

```brew```

A list of documentation options should appear if it has been installed. We have one more command to run to make sure everything is working, which is:

```brew doctor```

With Homebrew installed, we now have to install wget. This is now an easy step.

```brew install wget```

It will proceed to download the most recent version of wget, which is wget 1.14. After the script stops running, and you are back to your main window, enter the following command into the terminal:

```wget```

If wget has installed, you will see:

```$ wget: missing URL```  
```Usage: wget [OPTION]... [URL]...```  
```Try 'wget --help' for more options.```

If wget is not installed on your system it will respond with:

```$ command not found.```

At this point, however, wget should be installed successfully. If it is not installed, go through each of the steps above to make sure you did not make a mistake installing Homebrew.

## 4. Workshops <a name="workshops"></a>

Does your research require you to build an archive of data from public websites? In this workshop attendees will learn how to automatically download webpages with the wget program in your command line interface without going through the tedious process of manually downloading webpages. Attendees will also be guided through the process of cleaning up data once it’s downloaded.

For this workshop we are going to walk through a few exercises using wget in your operating system's command line interface: terminal for Linux and OS X and Ubuntu for Windows. If you have followed the setup instructions to install wget on your Linux, Windows, or OS X machines then you are ready to begin the workshop. 

### 4.1 Warm-Up <a name="warmup"></a>

Before we begin there are a couple of exercises we need to go through before we can start the workshop. The first exercise is to make sure wget is installed. In the command prompt type in the following command and hit enter:

```wget --version```

Alternatively, you can type an abbreviated command and hit enter:

```wget -V```

Note that the uppercase ```-V``` is important. If you type ```-v``` you will receive an error message. Upper case and lower case characters are important with wget, like most programs in the command line.

After you type the command and hit enter you should receive a version message followed by information about your installation of wget, including copyright, license, and developer information:

```GNU Wget 1.19.4 build on linux gnu.```

Now that we know wget is installed and ready to go on your computer for some digital research we can try a few other commands. Another command that is really useful if you need instructions to help you craft your command is the help function. In the command prompt type in the following command and hit enter:

```wget --help```

Alernatively, you can type an abbreviated command and hit enter

```wget -h```

Note that the lowercase ```-h``` is important. If you type ```-H``` you will invoke the 'go to foreign hosts when recrusive' command and retrieve an error code because you have completed your command string. 

After you type in the command and hit enter you should receive a version message followed by a list of commands you can invoke using wget:

```GNU Wget 1.19.4, a non interactive network retriever.```  
```Usage: wget [OPTION]... [URL]...```  

You will notice this second line starting with ```Usage``` shows you how to use wget. You begin with the command ```wget``` followed by your options and ends with the URL where you want to retrieve web data. The options are listed in the command printout after you enter ```wget --help``` or ```wget -h```, which includes commands for:

Startup  
Logging and input file  
Download  
Directories  
HTTP options  
HTTPS (SLS/TLS) options  
HSTS options  
FTP options  
FTPS options  
WARC options  
Recursive download  
Recursive accept/reject  

You will observe that there are several command options, sometimes dozens, under each category. The list of commands might seem overwhelming, but rest assured we will only be using a handful in this workshop. It is important, however, to take note of the range of options available to you in wget because there is likely an option or string of options that will enable you to complete your digital research.

### 4.2 Retrieve a Webpage or File <a name="exercise1"></a>
Let's take an example file from the web. Say you want to download a news article hosted on *The Medium* website, UTM's student newspaper. First though, we need to create a folder for you to deposit your data. In your working directory, make a new directory. Let's call it wget-medium. To make sure you are in your home directory, type in and enter the following command:

```cd```

The command ```cd``` is the 'change directory' command. You use this command to navigate through your folders. When you type in ```cd``` you are automatically redirected to your home directory. When you type ```cd ..``` you navigate backwards one directory. 

To create a new folder in your home directory with the folder name wget-medium, type in and enter the following command:
 
```mkdir wget-medium```

The command ```mkdir``` is the 'make directory' command. You have probably noticed that many commands are just abbreviations of actions. If you ever need a list of commands for your terminal simply type and enter:

```help```

And a list of commands will print out followed by the version of your terminal. At the time of writing this workshop my version was 3.2.57 on a 64 bit Apple desktop:

```$ GNU bash, version 3.2.57(1)-release (x86_64-apple-darwin19)```

Now that you have created the directory, let's navigate to the director. Type in and enter the following command:

```cd wget-medium/```

The ```cd``` command also can navigate you to a folder from the folder you currently reside. Next we want to retrieve a news article from UTM news. First you need to get the url and then type in and enter the following command:

```wget https://themedium.ca/news/mississauga-asks-students-for-feedback-on-living-green/```

After some initial messages, you should see the following (however, some figures, dates, and some details will be different):

```--2019-10-09 13:14:35--  https://themedium.ca/news/mississauga-asks-students-for-feedback-on-living-green/```  
```Resolving themedium.ca (themedium.ca)... 104.28.7.47, 104.28.6.47```  
```Connecting to themedium.ca (themedium.ca)|104.28.7.47|:443... connected.```  
```HTTP request sent, awaiting response... 200 OK```  
```Length: unspecified [text/html]```  
```Saving to: ‘index.html’```  
```index.html              [ <=>                ] 113.03K  --.-KB/s    in 0.04s```  
```2019-10-09 13:14:58 (2.85 MB/s) - ‘index.html’ saved [115746]```

What you have done is downloaded just the raw text file of the UTM News article. If you open the HTML file it will appear in your browser. You now have a copy of the UTM news article that you can add to your research data.

### 4.3 Retrieve Multiple Files from a Website <a name="exercise2"></a>
Let's say you want to download copies of all The Medium's news articles. To do this we will need to enter in a few options to our wget script.

Wget operates on the following general basis:

```wget [OPTIONS] [URL]```

In the previous exercise we learned about the ```[URL]``` component of wget. ```[OPTIONS]```, however, give the program a bit more information about what exactly we want to do. the program knows that an option is an option by the presence of a dash before the variable. This lets wget know the difference between the URL and the options.

So let's now learn a few other commands to write a wget script to download all The Medium's news articles.

```-r```

Recursive retrieval is the most important part of wget. What this means is the program begins to follow links from the URL you provide and downloads them too. You will notice the URL we used is part of the ```/news/``` folder of the UTM website. So, if we use ```-r``` on the ```/news/``` folder it will download all the news articles in that folder. However, it will also follow any other links in the news articles that point to other websites. By default, ```-r``` sends wget to a depth of five sites after the first URL. This means it follows links, to a limit of five clocks after the first URL. At this point, your wget script could capture a lot of data you do not want. So, we need a few more commands.

```-np```

The command  ```-np``` is the 'no parent' command which can also be written as ```--no-parent```. This is an important command as it tells wget to follow links, but not beyond the last parent directory. In the case of this exercise, that means it won't go anywhere that is not part of the https://themedium.ca/news/ hierarchy. The no parent command is crtitical for delineating your search.

Finally, it is important to add in a few commands that slow down your wget script. Web servers handle a lot of traffic and the wget program will download everything you command it too immediately unless you tell it to wait. There are two commands you can use to slow downloads:

```-w [SECONDS]```  
and  
```--limit-rate=[KB/S]```  

The command ```-w``` is the 'wait' command and delays the download of each link by seconds. A good wait time is 2 seconds (```-w 2```) as it roughly represents how long it would take you to click from link to link. On rare occasions, you may come across a site that blocks automated downloading altogether. The website’s terms of service, which you should consult, may not mention a policy on automated downloading, but steps to prohibit it may be built into their website’s architecture nonetheless. In such rare cases, you can use the command ```--random-wait [SECONDS]``` which will vary the wait by 0.5 and 1.5 times the value of seconds you provide.

The command ```--limit-rate``` is the 'limit rate' of download speed for wget. You don't want to use up too much of the servers' bandwidth. The 'limit rate' command will limit the maximum downalod speed in kb/s. A good rate is around 200 kb/s for small files, but it's up to your discretion when setting a download speed limit. For this workshop, however, we are going to set our limit rate to 20 kb/s in case there are several people completing this exercise at the same time.

So, we are now ready to download news articles from The Medium. Note, the trailing slash on the URL is critical as it tells wget we are accessing news articles in a directory. If you omit the slash wget will think you are wanting to download a file. The order of the options does not matter, but here is a command you type in and enter:

```wget -r -np -w 2 --limit-rate=20k https://themedium.ca/news/```

The download will be much slower than before, but your terminal will being downloading all the news articles on *The Medium* website. When it is done you should have a directory labelled ```themedium.ca``` that contains the ```/news/``` sub-directory. This directory will appear in the location that you ran the command from your command line, so likely is in your ```USER``` directory. Links will be replaced with internal links to the other pages you have downloaded, so you can have a fully working themedium.ca site of news articles on your computer.

If for whatever reason you want to cancel the search you simply hit ```CTRL``` and ```C```together.

### 4.4 Mirror a Website <a name="exercise3"></a>
Let's say you want to copy an entire website, you would use the mirror function by using the command:

```-m```

The ```-m``` command mirrors an entire URL, and is especially useful for backing up an entire website. For digital research, this can be quite useful if you're doing historical research of social groups whose online presence is known to disappear, or who frequently change and update their web content. Mirror introduces the following set of commands: time-stamping, which looks at the date of the site and doesn’t replace it if you already have that version on your system (useful for repeated downloads), as well as infinite recursion (it will go as many layers into the site as necessary).

The command for mirroring *The Medium* website is:

```wget -m -w 2 --limit-rate=20k https://themedium.ca/```

As in the previous exercise, the download will be very slow, but The Medium website will be perfectly mirrored when complete showing all of the sub-directories. It is difficult to gauge how long this will take, but mirroring websites can sometimes take hours, even days depending on how much web content is on the website. This is especially the case for websites with audio-visual material.

## 5. Final Thoughts <a name="final"></a>

As you become increasingly comfortable with the command line, you will find wget a helpful addition to your digital research toolkit. If there is an entire set of archival documents that you want to download for text mining, if they’re arranged in a directory and are all together (which is not as common as one might think), a quick wget command will be quicker than scraping the links with Python. Similarly, you can then begin downloading things directly from your command line: programs, files, backups, etc. You will soon find that wget may be a first option for you to research all kinds of web content!
