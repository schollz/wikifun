# wikifun

## Basic basic idea

You are given a Wikipedia page. Your page is linked to by another page that is hidden to you and all other users. You try to guess the page that links to your page. You can gather information from other people or by exploring a map and looking for signposts. First one to guess the page that links to your page, wins.

# How it works

## Basic idea

User goes to webpage and enters a round of play. Each round of play is 60 minutes. User is given a simple avatar and put on **game board** (80 x 80 grid with simple maze). The game board has walls which hide spaces behind them, but otherwise you can see the section of grid they are in (10 x 10) out of entire map.

User is given the number of letters for the **solution phrase** e.g. `_ _ _ `. The solution phrase is a Wikipedia page, in this example the answer is "cat". The goal is to guess the solution phrase before your opponents do. 

User is also given one piece of **information**: a Wikipedia page that linked *from the page of the solution phrase*. For example, for the solution phrase "cat", the User is given the title of a page that linked *from* from the Wikipedia page for "cat", e.g. "carnivorous", "mammal", "feline", or "vermin." 

The User can **explore** the game board in order to acquire more information (they can also read the Wikipedia page which might give clues to solve the solution phrase). Exploration occurs by moving around a simple maze in a game board. During exploration, Users can choose to Share or to Not Share. If a User sees another User and they both are choosing to Share, then they automatically exchange information. The game board also includes "signposts" (essentially not-yet-activated users) that always share information once in view.

## Strategy

Their are three inherent strategies: 

1. Explore the game board fastest to find all the signposts to get information, without revealing any information you have,
2. Interact with as many users as you can to gain information (while revealing your own) in order to guess fastest,
3. Read the given Wikipedia page you have received and try to make your best guess of what the solution phrase is that linked to it.

(1) is a good strategy if you have been given particularly revealing information. (2) is a good strategy if the information you have is not very good.  (3) is a good strategy if you think you are good at parsing information, or if it is something you are particularly well-versed in or good at researching.

# Decisions

These are some game decisions that can be made (and maybe can be changed):

- During interaction, random information is shared (encourages strategy swapping)? OR user specifies the information that is shared? ZACK: For starters, user only shares their given information.
- User can share information learned from interaction? OR User can only share their information given at the beginning of the game? ZACK: For starters, user only can share the information gained at beginning.
- Information is the page name? OR information is a random fact on the given page? ZACK: For starters, information is the page name.
- Should a radar be added to help bolster user-finding (to make it easier than signpost finding to encourage sharing)?

# Implementation

## Components 

Each of these components might be justified for having their own set of folders and their own set of tests.

- [ ] Chatroom-style websockets for handling gameboards and user interactions
- [ ] Gameboard (maze generation, API for getting/setting position, radar)
- [ ] Wikipedia API for getting solution phrases
- [ ] General utilities
- [ ] Front-end HTML page for connecting to server
- [ ] Leaderboard

## Users and signposts

A signpost is just an unactivated user that does not move and always shares, even if the interacting user is not sharing. When a new user enters, they basically are given control of a signpost. That is, they start in the position of the signpost, and they get the information that the signpost has.
 
## Sharing information

Users have a On / Off button for sharing information. If On, they will receive information from other Users who also have their sharing set to On, when they are within their local zone. Information from signposts is always shared, regardless of the User setting.
