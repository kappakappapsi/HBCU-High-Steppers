Group Project - README Template
===

# HBCU High-Steppers

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
Social media for bands that allows for people to view/upload band videos. 


### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** Photo & Video / Social 
- **Mobile:** Allows you access on various forms of electronics.
- **Story:** Allows users to share their musical talents/ventures with HBCU bands who have similar interests
- **Market:** Anyone with an interest in marching bands.
- **Habit:** Users can post throughout the day many times. Users can explore other lesser know bands to increase their exposure to other opportunities.
- **Scope:** HBCU High-Steppers is an app that allows you to post videos of your band and allows other users to send audition tapes or follow their favorite bands.

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* [fill in your required user stories here]
- User can sign up to create a new account using Parse authentication

- You'll need to setup the Parse SDK and connect to the Heroku server you've just setup. See this guide on Enabling Client SDK integration.
 - Initializing the SDK and setting up Parse Login
- User can log in and log out of his or her account

- The current signed in user is persisted across app restarts 

- User can take a photo, add a caption, and post it to "Instagram" 

**Optional Nice-to-have Stories**

* [fill in your required user stories here]
- User sees app icon in home screen and styled launch screen that looks like the real Instagram page.

- Style the feed to look like the real Instagram feed. (2 points)

- After the user submits a new post, show an indeterminate progress bar while the post is being uploaded to Parse 

### 2. Screen Archetypes

* [Screen One Login Screen]
   * [Screen one will contain Username and login]
   * ...
* [Screen Two Home page]
   * [This page will view content that other users post]
   * ...
   *[ Screen three Profile page]
    [ Screen will contain users vidoes profile pic and who they follow ]
    [ screen four Upload page]
        [ screen will allow you to upload vidoes]
    
### 3. Navigation

**Tab Navigation** (Tab to Screen)

* [Login Screen]
* [Home/Feed Page]
* [Profile Page]
* [Upload Page]

**Flow Navigation** (Screen to Screen)

* [Login Screen]
   * [Login Screen]
   * username and password entry
* [Home page]
   * [Home page]
   * This page will view content that other users post
* [Profile Page]
    * [Profile page]
    * screen will list user vidoes, profile picture, and followers
* [Upload Page]
    * [upload page]
    * screen will allow you to upload vidoes

## Wireframes
[Add picture of your hand sketched wireframes in this section]![](https://i.imgur.com/bTv6UVY.jpg)

<img src="https://imgur.com/9TncPUs" width=600>

### [BONUS] Digital Wireframes & Mockups

### [BONUS] Interactive Prototype

## Schema 
| property      | type           | description
| ------------- | ---------------| ---------------
| objectid      | string         | id for user post 
| author        | pointer to user| image author
| video         | file           | video user can post
| caption       | String         | caption by user
| commentsCount | Number         | number of comments that has been posted to an image
| likesCount    | number         | likes for post
| createdAt     | dateTime       | date when post is created (default field)
| updatedAt     | dateTime       | date when post is last updated (default field)

### Models
[Add table of models]
### Networking
List of network requests by screen

Home Feed Screen
(Read/GET) Query all posts where user is author
    let query = PFQuery(className:"Post")
    query.whereKey("author", equalTo: currentUser)
    query.order(byDescending: "createdAt")
    query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
    if let error = error { 
      print(error.localizedDescription)
    } else if let posts = posts {
      print("Successfully retrieved \(posts.count) posts.")
  // TODO: Do something with posts...
   }
  }
* (Create/POST) Create a new like on a post
* (Delete) Delete existing like
* (Create/POST) Create a new comment on a post
* (Delete) Delete existing comment
* Create Post Screen
* (Create/POST) Create a new post object

Profile Screen
    (Read/GET) Query logged in user object
    (Update/PUT) Update user profile image

- [OPTIONAL: List endpoints if using existing API such as Yelp]
