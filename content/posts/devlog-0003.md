+++
date = '2026-10-06T17:36:03-07:00'
draft = false
title = 'Acquired Tastes: Tag-Based Attributes and Preferences'
+++

## Identifying the Core Gameplay Loop
We knew very early on that the core gameplay loop of our game would look something like this:
- The player receives clues and hints from various sources as to NPCs' personal food preferences.
- The player takes what they have learned and builds a menu to appease as many attendees as possible.
- The player is scored on their performance.

With that core loop in mind, it became apparent that a strict tag-based system had to be employed in order to match character preferences with dish attributes and that the final scoring would be based on a comparison of each attendee's preference list and the assembled menu's attributes list.

## Creating a Tag Database
We had to create a variety of "tags" that would be represented in each dish's attributes and each individual character's food preferences. We started out by defining broad categories that the tags could fit into, eventually settling on the following: **Flavor**, **Aesthetic**, **Key Ingredients**, **Texture**, and **Quirk**.

A dish's attributes or a character's preferences may contain multiple tags from any category, so it was important that each tag was distinct and well-defined. Conversely, the tags have to be broad enough to be well-represented across the various dishes and flavors.

For example, we initially had separate texture tags for "creamy" and "smooth", but found that a dish with one of those tags almost always also possessed the other, making them redundant. Similarly, if only one character likes "sour" foods, then it becomes much harder for the player to both identify and account for that one singular preference.

After much deliberation and multiple iterations, we eventually landed on the following tag database:

### Flavors
| Tag | Definition |
| --- | ---------- |
| Sweet | Sweet in flavor, characterized by the use of sugar, honey, or fruit as sweetening agents. |
| Salty | Salty in flavor. |
| Umami | Characterized by a savory flavor often associated with soy sauce, mushrooms, and certain cheeses. |
| Sour | Sour or acidic in flavor. |
| Savory | Characterized by savory flavors not represented by umami, often associated with meaty or brothy flavors. |
| Spiced | Incorporates both spicy (hot) foods and foods that heavily integrate strong spices such as cinnamon, cloves, pepper, nutmeg, etc. |

### Aesthetics
| Tag | Definition |
| --- | ---------- |
| Rich | Integrates expensive or rare ingredients. May be simple in preparation, but only affordable to the very wealthy. |
| Simple | Foods using common or affordable ingredients, often eaten by the common people. |
| Traditional | Foods with a long history or otherwise of noted cultural importance. |
| New | Integrates novel ingredients or cooking methods. |
| Exotic | Foods originating from far-off lands which include non-native ingredients. |
| Extravagant | Food prepared for spectacle. |

### Key Ingredients
| Tag | Definition |
| --- | ---------- |
| Seafood | Made with fish or other aquatic animals. |
| Poultry | Fowl and reptiles. |
| Meat | Meat from terrestrial animals (i.e., red meat)
| Exotic Beasts | Meat from particularly strange or unusual creatures |
| Vegetables | The edible, non-fruiting bodies of plants. |
| Fruit | The edible fruiting bodies of plants (excluding tomatoes). |
| Mushrooms | Edible fungi. |
| Strange Things | Characterized by particularly weird or offputting primary ingredients. |
| Dairy | Milk, cream, cheeses, eggs, etc. |

### Texture
| Tag | Definition |
| --- | ---------- |
| Smooth | Of consistent and uninterrupted texture; easy to swallow. |
| Chewy | Requires significant masticating to properly consume. |
| Crispy | With notable and audible crunch when eaten. |
| Wet | Of a watery consistency (e.g. soups, broths, and sauces). |
| Flaky | With distinct layers that collapse independently when eaten. |
| Succulent | Releases juices upon being bitten into. |

### Quirks
| Tag | Definition |
| --- | ---------- |
| Face | Contains a visible face from the animal from which it originated. |
| Aspic | Contains or is otherwise reminiscent of gelatin or aspic. |
| Healthy | Believed to have health benefits. |
| Temperature | Served notably or unusually cold or hot. |

**NOTE:** *Some of these tags are relative or contextual to the fictionalized kingdom we have created for this game, which is heavily inspired by Mediterranean nations such as Greece, Italy, and Spain, and thus is admittedly from a Western-centric perspective.*

## Creating Character Taste Profiles
After the tag database is defined, we then went through and assigned taste preferences for each of the 8 characters we have in the game. Although characters could have any number of likes or dislikes, we attempted to stratify the characters by night so that with each passing feast in the game, the difficulty scales. For characters introduced on Night 1, their net preference value equals 4. For characters introduced on Night 2, their net preference value equals 3. Lastly, for characters introduced on Night 3, their net preference value equals 2. This means that as you progress through the game, newer characters are more difficult to please. However, these characters also tend to have a smaller impact on the total overall score.

## Scoring the Menu
Given such a short deadline, we decided to take as simplistic approach as possible to designing the scoring system, as we will not have much time to test and rebalance. In this simple scoring system, each character is assigned a value of -1, 0, or 1 for each tag, representing negative, neutral, or positive preference respectively. Dishes are then assigned boolean values for each of the tags.

Although there are no strict minimums or maximums for how many attributes a dish may have or how many preferences a character may possess, we attempted to use discretion in order to achieve some semblance of balance. Generally speaking, dishes are restricted to two tags per category with a few exceptions. For characters, we attempted to achieve certain thresholds of net preference value based on the difficulty tier of the character (i.e. characters that are more difficult to please have a lower net preference value).

For each in-game night, after a menu is declared, the player sees a scorecard depicting how well they did. We decided to show the player three metrics: 
- an overall score
- the most-liked dish
- and the least-liked dish

The overall score, depicted as a 5-star rating, is derived by simply calculating the net preference value of all characters attending the feast for the dishes served that night, divided by the maximum possible value. The chart below shows the possible distribution of scores for Night 1. As you can see, the highest possible score is 32 points, which is possible to achieve from 8 different dish combinations. This means that selecting any of these 8 dish combinations on Night 1 would earn the player 5 stars.

![Histogram](images/night-1.png)

The most-liked dish is the dish with highest net preference value while the least-liked dish is the dish with the lowest net preference value. Next to the most-liked dish, the player is shown character portraits of each character with a positive preference value for that dish and, similarly, for the least-liked dish the player is shown characters with a negative preference value for that dish.

Apart from providing direct feedback for the player to gauge how well they interpreted the various clues they were given for that feast, we hope that this scoring feedback also acts as supplementary clues themselves, providing usable information that the player can carry over to future levels of the game. We strongly believe that rewarding players for playing the game the way you want it to be played creates a healthy and cyclical ecosystem that fortifies and validates the core gameplay loop. If we have been successful in achieving that, then the game should be fun and rewarding.