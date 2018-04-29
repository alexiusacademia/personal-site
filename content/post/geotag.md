---
title: "Geotag"
date: 2018-04-29T11:31:59+08:00
draft: false
image: "images/geotag.png"
categories: ["projects"]
---
**Geotag** is a simple web-based application I wrote using PHP and MySQL for backend.

Before, there was a web app owned by google called picasaweb. This is where they hosts some of google user's photos. One of the best feature of this application is that in every album, you can generate a kmz (google earth file) file where all the important information of every image is referenced. You can use this file and import to Google Earth and you can see all the images of the album in which you downloaded the kmz file.

### The Problem

Since May 2016, Google started retiring the picasaweb application to focus on a single photo service, the Google Photos. Since then, some of those that uses that particular feature of picasaweb get's some frustration, among them is me. I use that service intensively for reporting.

### Solution

With this problem, me and my colleagues never lose hope. We tried and tried looking for some existing solution to replace the feature of picasaweb. We found Google's Panoramio. That was almost working until it was also retired by Google. We tries until we cannot find any more solution. And so it came to me, why not build my own app that features that particular requirement.

And so I started planning the solution. I drafted an app with **python** but quickly quitted as I can't find a hosting easily that hosts python. Most of the hosting I knew offers PHP. And so I revised all my code to work on PHP and MySQL.

The application's feature is at the most basic it can be. It features creating and account with Google, allows users to create albums, upload multiple images to each albums. But the most important feature of this application is the downloading of the kml file of an album.

Before the app creates a download link, it goes to a stage where it parses each images in an album, creates a kml (keyhole markup language) file then presents its download link.

The app is still active and can be found at [https://geotag.alexiusacademia.com](https://geotag.alexiusacademia.com)

For those who are interested in the app, you can try it free. I will be leaving the app online for some time for evaluation purposes and maybe end it or move to other server when I can afford it as it may take a very large amount of web space and I can't support it in my personal site anymore. Please let me know of what you think of it. Thanks!
