+++
date = '2026-09-19T13:29:13-07:00'
draft = false
title = 'Limited Time'
+++

As this game is being made as part of a class assignment, we have been given only 9 weeks to design, create, and publish it. While we are only 2 weeks in at this point, we are humming right along and excited to show you the progress thus far. The next few dev logs will all be about designing the mechanics and systems that form the game. For this first one, the central theme is "limited time" -- we will discuss how the limited time we have been given to make this game affected design decisions and how we decided to incorporate limited time mechanics into our game.

## Planning the Game
The idea for *A Feast Most Deadly* spawned from a simple thought: what if you took the mechanics of *Papers, Please* but set it in a pre-industrial castle where you are setting a menu for each night's feast?

Players have to figure out the wants, needs, and dislikes of the various attendees of the dinner and then build a menu based on what they learn. At its core, it is a puzzle game with deductive reasoning. On the surface, it is a light workplace simulation.

Given a tight timeline (and the fact that this is not our full-time job), we knew we had to set strict limitations on the game design. Very early in the process, we decided on the following restrictions:
- The game takes place over a course of only 3 days. That means there are only 3 meals to plan.
- The meals consist of only 3 courses: 1 main dish, 1 supporting dish, and 1 dessert.
- There will only be a maximum of 10 interactable characters in the game.
- Player interactions are limited to: talking to NPCs and reading documents.

We felt that given the timeline, our schedules, and our capabilities, that this is a game we will be able to complete in 9 weeks. After settling on Godot as our game engine and assigning roles, we got to work designing the game.

## Designing the Game
From the outset, we imagined the gameplay loop to look like this:
- At the start of the day, the player receives a list of attendees who will be at that night's dinner and a list of possible dishes they can choose from. They may also receive some information surrounding the context of that night's dinner (e.g., maybe it is the Princess's birhtday) which may provide a clue as to how to approach the day.
- Players spend the day talking to NPCs -- including the royal family, visiting guests, and castle servants -- to collect information that may be helpful in crafting the dinner menu. This information may take the form of rumors, hints at personal preferences, or reports from the kitchen staff.
- The player also has access to a dossier which not only logs all of the information they learned from speaking to the characters, but also descriptions of all the possible dishes.
- After gathering information, the player builds the menu by selecting 1 main dish, 1 supporting dish, and 1 dessert.
- Dinner is served and the player receives a report card indicating how each attendee felt about the meal and an overall grade based on accumulative satisfaction.

## Limiting Time
While the restrictions listed in the previous section were self-imposed based on scope, we believe the foundation of good design is imposing restrictions on the *player* that induce both a challenge and creative thinking. We knew that if we let players uncover every possible hint and rumor, then assembling the menu would be too easy.

We considered two possible ways to functionally limit how much a player can accomplish in an in-game day: a literal "timer" that ticks down in real-time or by setting a hard limit on the number of "actions" a player can take.

We knew that each of these options would present differently to the player. A ticking timer would make the game feel more *intense* and *frantic*. Limiting the player's actions (while giving them unlimited time) would make the game feel more *deliberate* and *methodical*. We decided the latter is more of what we are hoping to achieve.

While it still requires some more testing, we have settled on a limit of 3 "actions" per day. An "action" is consumed by talking to an NPC. Each dinner has a minimum of 5 attendees, so that means that not every attendee can be spoken to in a day. This added challenge not only makes it more rewarding when the player is able to deduce the "correct" solution, but it also gives the game replayability value for players that wish to see how different choices affect their decisions.

We are currently toying with the idea of having certain characters cost more than 1 action to talk to, but the information they provide would be more valuable than the information provided by standard NPCs. For example, you may have a visiting dignitary who brought an exotic fruit with them. Talking to them may cost all 3 actions, but in return they gift you the fruit which will prove to be universally loved at that night's feast.

Similarly, some characters may cost 0 actions to speak to. This would likely be reserved for various castle staff members that are not attendees of the dinner. Their information could be vague, untimely, or maybe even incorrect.

We still have some playtesting and balancing to do, but we are excited about the ideas we have on the table right now. Puzzles should be all about fitting pieces together. The deductive logic system employed by our game isn't the most challenging or complex, but we think if we can manage to capture that feeling accomplishment once you figure it out, then we have done our jobs.

Stay tuned for the next dev log as we discuss the scoring system and how sometimes the goal isn't always to score the most points.