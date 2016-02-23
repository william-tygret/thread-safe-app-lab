---
title: Reworking provided code to be thread-safe
type: lab
duration: "1:25"
creator:
    name: Yuliya Kaleda
    city: NYC
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Reworking provided code to be thread-safe

## Introduction

> ***Note:*** _This can be done independently._

In this lab, you will refactor the code of the app to make it thread-safe.

In the starter code provided, there is an application with an activity that contains an ImageView and a button. When the button is clicked, the gallery comes up and lets the user choose an image to set in the image view as a profile picture. When the image is chosen and set, it gets saved to a file.

Every time the user opens the app, the image gets loaded from the same file that it got saved to when the user chose the image for the first time. If the user has never updated the image, he/she should see a placeholder, which is located in the drawable/ folder.

Everything is done on the main thread but saving an image to a file should not be done on the main thread as it may be a long-running operation and might block the user interaction - it is better to be done on the background thread.

Refactor the starter code so that when the image gets changed, it should get saved to a file on the background thread using AsyncTask and upon saving the image, the user will receive a toast.

## Exercise

#### Requirements

- the app should be responsive all the time
- saving an image should be done on the background thread
- when the image is saved, provide the user with a toast feedback prompting that the image has been saved to a file and set as a profile picture

Bonus:

- Display a thumbnail of the previous profile picture somewhere on the screen

#### Starter code

Import the [starter code](starter-code) provided.  Take a look at the breakdown below:

- Main Activity - the activity where all the logic happens: the user can change the profile image, it gets set as a profile image and saved to a file;
- Picture Util - helper class that deals with saving and loading images; you do not have to modify anything in this class;
- activity_main.xml - layout file for Main Activity; you do not have to modify it.

#### Deliverable

The app should look the same way and perform the same operations/have the same features, only thread safe. Isolate saving a profile image to a file into a separate background thread and make sure you show a toast feedback on the UI thread.
