# Pet Connect

## Table of Contents
1. [Overview](#Overview)
2. [Product Spec](#Product-Spec)
3. [Wireframe](#Wireframe)
4. [Schema](#Schema)

## Overview

### Description

Anonymously lets users swipe in hopes of finding a mutual connection for their pets, from the input from user. Can be used as a mating app for pets, or a way to connect pets with owners and other pets.

### App Evaluation 

- Category: Social Networking / Pets/Animals 
- Mobile: This software will be designed specifically for smartphones, IOS and Android users. With similar functionalites if used on a computer similar as tinder or other related applications. Functionality should not be restricted to mobile devices, but may likely include more functionality in desktop and mobile.
- Story: Analyzes users animal preferences and connects them to users with the same or similar animal prefences. Once connected user then has the option to message said user. 
- Market: Any individual who owns an animal can use this app, they will be grouped by the animal they signed on with.
- Habbit: This application may be used as often or as often as the user desired, based on how broad their social life is, and exactly what they want for their animal.
- Scope: We would start pairing users by their animal prefrences. 

## Product Spec

### 1. User Stories

* User logs into application and views the feed for potential pet matches
* User picks among animal groups 
* Matches have a chat channel, with the option to get to know each other, along with the option to unmatch
* User profile page
* Settings screen (User can update information)

### 2. Screen Archetypes

* Login
* Register - User can register or login to their account
* Messaging Screen - Chat for matched users to communicate one-on-one.
  * Only available if two users are matched.
* Chat Screen - Allow users to view their open chats
* Profile Screen
  * Allow users to view and update their information.
* Main Feed Screen - Feed of pets that a users pet can connect with based on their pet type.
* Settings Screen - Update user information.

### 3. Navigation

**Tab Navigation** (Tab to Screen)
* Profile
* Feed
* Chat

**Flow Navigation** (Screen to Screen)
* Messages -> User taps on an open chat on the Chat Scree and is able to view the messages with the other party
* Settings -> Toggle settings

## Wireframe

### Digital Wireframe & Mockups
<img src="https://media.giphy.com/media/USmBixENt5sQfCZmGF/giphy.gif" alt="Walkthrough">

## Schema

### Models
#### User

  | Property    | Type    | Description |
  | ----------- | ------- | ----------- |
  | uid         | String  | unique id for registered user |
  | email       | String  | email provided for user registration |
  | displayName | String  | user display name  |
  | fullName   | String  | user enter full name |
  | age    | INT  | user enters age |
  | isMale    | Boolean  | user chooses gender |
  | current_longitude   | String  | user current longitutde |
  | current_latitude   | String  | user current latitude |
  | status   | String  | user status |
  | isOnline   | Boolean  | is user online |
  | profileImageUrl   | Image  | user profile image url |
  | latest   | String  | user latest location |
  | online   | Boolean  | is user online |
  | typing   | String  | is user typing |
  
#### newMatch

  | Property    | Type          | Description |
  | ----------- | ------------- | ----------- |
  | objectId    | String        | unique id of match |
  | postCreator | Point to user | email provided for user registration |
  | matchedUser | Point to user | user that swiped right |
  | matchedAt   | DateTime      | date when users were matched |
  | isMatched   | Boolean       | if the users are still matched or not |
  
#### Post

  | Property    | Type          | Description |
  | ----------- | ------------- | ----------- |
  | objectId    | String        | unique id of post |
  | creator     | Point to user | post creator |
  | image       | File          | image of pet |
  | caption     | String        | caption of post |
  | createdAt   | DateTime      | date when post was created |
  | updatedAt   | DateTime      | date when post was last updated |
  
#### Inbox

  | Property    | Type                     | Description |
  | ----------- | -------------            | ----------- |
  | objectId    | String                   | unique id of chat session |
  | createdAt   | DateTime                 | date when chat session was created |
  | messages    | Array of Message objects | list of messages exchanged between the users in the chat session |
  | from       | String           | unique user id sending message |
  | to       | String           | unique user id receiving message |
  | read       | Boolean           | if user read meassage |
  | date     | DateTime           | Time messgae was sent |
  
#### Message

  | Property    | Type          | Description |
  | ----------- | ------------- | ----------- |
  | objectId    | String        | unique id of chat session |
  | createdAt   | DateTime      | date when message was created |
  | updatedAt   | DateTime      | date when message was last updated |
  | text        | String        | content of message |
  | sent        | Boolean       | indicates if message was sent properly |
  | author      | Point to user | author of message |
  
  
## Networking
### List of network requests by screen

  - Login Screen
    - (Create/POST) Login User
    - (Create/POST) Register User
  - Home Feed Screen
    - (Read/GET) Retreive all posts
  - Match Screen
    - (Create/POST) Create match between two users
  - Chat Screen
    - (Read/GET) Retreive all chats a user has open
  - Messaging Screen
    - (Read/GET) Messages from chat session
    - (Create/POST) Create a new message
    - (Update/POST) Update a message
  - Settings Screen
    - (Update/POST) Update user information
  
## Milestone Deliverables #1

We added the ability for users to create an account and login. We also implemented a base tab bar controller to build off of for our next sprints.

### Progress Walkthrough
<img src="https://cs-2355-gifs.s3-us-west-1.amazonaws.com/Apr-09-2020+23-07-46.gif" height="400" alt="Walkthrough">

## Milestone Deliverables #2
Users are now able to search for other users or view a list of users. Eventually, we will implement a different label that indicates whether the user is a pet owner or a breeder.

### Progress Walkthrough
<img src="https://cs-2355-gifs.s3-us-west-1.amazonaws.com/Apr-29-2020+23-15-32.gif" height="400" alt="Walkthrough">

## Milestone Deliverables #3
Users are now able to chat with each other. This will change once we implement the swiping feature which will only allow matched users to interact with each other.

### Progress Walkthrough
[Standard text message](https://cs-2355-gifs.s3-us-west-1.amazonaws.com/Apr-29-2020+23-10-39.gif)
[Photo library message](https://cs-2355-gifs.s3-us-west-1.amazonaws.com/Apr-29-2020+23-13-35.gif)

Users are also able to take photo and video messages with their device.

