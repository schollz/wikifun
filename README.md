# wikifun

## Basic basic idea

You are given a Wikipedia page. Your page is linked to by another page that is hidden to you and all other users. You try to guess the page that links to your page. You can gather information from other people or by exploring a map and looking for signposts. First one to guess the page that links to your page, wins.

# How it works

## Basic idea

User goes to webpage and enters a round of play. Each round of play is 60 minutes. User is given a simple avatar and put on game board (80 x 80 grid). The game board has walls which hide spaces behind them, but otherwise you can see the section of grid they are in (10 x 10) out of entire map.

User is given the number of letters for the **solution phrase** e.g. `_ _ _ _`. The solution phrase is a Wikipedia page. The goal is to guess the solution phrase before your opponents do. Lets say, in this example, the solution phrase is `C A T S`.

User is also given a Wikipedia page that linked *from the page of the solution phrase*. For example, for the solution phrase "CATS", the User is given the title of a page that linked *from* from the Wikipedia page for "CATS", e.g. the user would get either "carnivorous", "mammal", "feline", or "vermin." 

User tries to guess the solution phrase using their information (e.g. by reading their wikipedia page and thinking about what pages linked to it) or they can **explore** the game board to find more information. 

Exploration occurs by moving around the game board. Users see one another on the board, and they also see **signposts**. Users can interact with another user *or* the signpost. When interacting with a **signpost** the User gains **information**. When interacting with a different user, the User gains **information** if both users mutually agree to divulge **information**.

**Information** can either be the page name from the wikipedia page, e.g. "vermin" (which links from "Cats"), or it can be some fact from the page, e.g. "The term is used to refer to a wide scope of organisms, including rodents, cockroaches, fleas, termites, lice, bed bugs and white ants." (which is a fact on the page for "vermin" that links to "cats"). With enough information, you may gather enough words to figure out what the solution phrase is.

## Strategy

Their are three inherent strategies: (1) explore the game board fastest to find all the signposts to get information, without revealing any information you have, or (2) interact with as many users as you can to gain information (while revealing your own) in order to guess fastest, or (3) read the given wikipedia page you have recieved and try to make your best guess of what the solution phrase is that linked to it.

(1) is a good strategy if you have been given particularly revealing information.

(2) is a good strategy if the information you have is not very good. 

(3) is a good strategy if you think you are good at parsing information, or if it is something you are particularly well-versed in or good at researching.

# Decisions

These are some game decisions that can be made (and maybe can be changed):

- During interaction, random information is shared (encourages strategy swapping)? OR user specifies the information that is shared?
- User can share information learned from interaction? OR User can only share their information given at the beginning of the game?
- Information is the page name? OR information is a random fact on the given page?
- Should a radar be added to help bolster user-finding (to make it easier than signpost finding to encourage sharing)?

# Implementation

Each of these components might be justified for having their own set of folders and their own set of tests.

- [ ] Chatroom-style websockets for handling gameboards and user interactions
- [ ] Maze generation for the gameboard
- [ ] Wikipedia API for getting solution phrases
- [ ] General utilities


