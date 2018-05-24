---
title: "Downloading Youtube Videos"
date: 2018-05-24T16:35:42+08:00
draft: false
image: "/images/downloading-youtube-videos/download-youtube.jpeg"
tags: ["tutorials", "youtube downloading"]
---

Hi everyone! In this tutorial, I will be showing you one of the methods in downloading videos from youtube.

### Why another tutorial?
I know you may have already seen a lot of tutorials regarding downloading youtube videos. That may be true, but most of them uses a web-based applications or online applications that can be used using your browsers. Most or all of these applications don't allow you in downloading any type of video. Some are protected, hence the application don't allow it. It can be a hassle especially if you really need something that can't be download, maybe for educational purposes. Because of this, I present to you this tutorial.

### About this tutorial
This tutorial is about using a commandline application in downloading videos. Don't worry about entering a command as I will guide you thoroughly step by step. All part of the tutorial is a direct to the point instructions with some explanations to make you clearly understand the process especially if you are not very familiar with the commandline or command prompt or the terminal in other operating systems.

### Required application
The software we are going to use is **youtube-dl**, an open source commandline program written in python. This software has a lot of features, from downloading single video to downloading a videos in a playlist.

### Installation
To use the software, we first have to install the binary.

#### Windows
In this installation, I assume that you are using a Windows Operating System. Your OS may vary from the screenshots below, but the process should be similar.
To download, go ahead and go to [https://rg3.github.io/youtube-dl/](https://rg3.github.io/youtube-dl/). You may see the page similar below:
<img src="/images/downloading-youtube-videos/youtube-dl-website.JPG" alt="youtube-dl website" width="550" />

From the page above, click on Download button and you will be directed to the download page
<img src="/images/downloading-youtube-videos/youtube-dl-download-page.JPG" alt="youtube-dl download page" width="550" />

For Windows, click on the <a href="https://yt-dl.org/downloads/2018.05.18/youtube-dl.exe">Window exe</a> link and the application will now be downloaded. You can move the downloaded file to your desired location or you can just let it be where it is. In my case, the downloaded file is in the Download directory in my computer
<img src="/images/downloading-youtube-videos/downloaded-file.JPG" alt="download directory" width="550" />

After you have decided if you are going to move it, let's get the location by right-clicking the youtube-dl.exe file and click on < Properties >
<img src="/images/downloading-youtube-videos/file-properties.JPG" alt="youtube-dl file properties" width="550" />

Now, look for the < Location > label and copy the location string, in my case, it is ```C:\Users\Windows 10pro\Downloads```.

The reason that we copied the location is the we are going to add the location to our Operating System's Environment Variables. This way, we can call the commands from the application wherever is out location at the command prompt/terminal.

Now let's open the control panel.
<img src="/images/downloading-youtube-videos/control-panel.JPG" alt="control panel" width="550" />

In the control panel, click on the link of < System and Security >
<img src="/images/downloading-youtube-videos/control-panel-system-and-security.JPG" alt="system and security" width="550" />

On the System and Security page, click on < System >
<img src="/images/downloading-youtube-videos/control-panel-system.JPG" alt="control panel system" width="550" />

Next, click on the < Advanced system settings >, the System Properties window will open
<img src="/images/downloading-youtube-videos/control-panel-system-properties.JPG" alt="system properties" width="550" />

Click on the < Environment Variables > button, a new window will appear
<img src="/images/downloading-youtube-videos/control-panel-environment-variables.JPG" alt="environment variables" width="550" />

On the System Variables box, scroll down to find the < Path > variable, click on it
<img src="/images/downloading-youtube-videos/control-panel-environment-variables-select-path.JPG" alt="path" width="550" />

Now click < Edit > button to open the edit page
<img src="/images/downloading-youtube-videos/control-panel-environment-variables-environment-variables-window.JPG" alt="edit environment variables" width="550" />

Then click the < New > button to enter a new entry
<img src="/images/downloading-youtube-videos/environment-variable-new.jpg" alt="new environment variable entry" width="550" />

In the space above, paste in the location of the file that we copied earlier then click < Ok > button. That concludes our Environment Variables operation. We can now proceed on downloading a video!

### Downloading a Video
Now, let's go to <a href="https://youtube.com">youtube.com</a> and look for a single video that we want to download. Select the video to go on the video's player page. Look for the URL in the browser and copy it.

<img src="/images/downloading-youtube-videos/youtube-url.JPG" alt="youtube url" width="550" />

Now let's open the command prompt/terminal,
<img src="/images/downloading-youtube-videos/open-command-prompt.jpg" alt="open command prompt" width="550" />

The above screen is taken from Windows, click on the Command Prompt
<img src="/images/downloading-youtube-videos/cmd.JPG" alt="cmd" width="550" />ode

Now let's assume that we are going to download the video on the default location above ```C:\Users\Windows 10pro\```,
type in ```youtube-dl -F [url]``` Replace the [url] with the URL you copied, the URL of the video you want to download. In my case,
<img src="/images/downloading-youtube-videos/youtube-dl-url.JPG" alt="url" width="550" />

After you typed the command, hit Enter on the keyboard. This command will fetch the available formats that can be downloaded for a video.
<img src="/images/downloading-youtube-videos/youtube-dl-format-code.JPG" alt="youtube-dl fetch formats" width="550" />

From the formats on the first column, you can select the code based on what format do you like. Remember to watch out for formats that says video only or audio only. In this example, I selected the format code 43, this will download a webm format video with the resolution of 640x360.

Now let's run the command for downloading a video. Remember to change the big letter ```-F``` to small letter ```-f```, followed by the code you chose and press Enter. This will now start the downloading process.
<img src="/images/downloading-youtube-videos/youtube-dl-download-command.JPG" alt="youtube-dl download command" width="550" />
<img src="/images/downloading-youtube-videos/youtube-dl-downloading.JPG" alt="youtube-dl downloading" width="550" />
<img src="/images/downloading-youtube-videos/youtube-dl-download-complete.JPG" alt="youtube-dl download complete" width="550" />

After downloading, you can now look at the location of the video.
<img src="/images/downloading-youtube-videos/download-location.JPG" alt="download location" width="550" />
<img src="/images/downloading-youtube-videos/file.JPG" alt="downloaded file" width="550" />

That's it! You have now downloaded a youtube video using youtube-dl software. Let me remind you that with this software, you can download any video from youtube without restrictions. Please use this at your own risk.

Thank you for reading. Please comment below for any questions you may have regarding this tutorial.
