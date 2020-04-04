---
layout: post
title:  "Social Deduction and Social Distancing"
date:   2020-04-04 14:00:00
permalink: social-deduction-and-social-distancing
categories: [board games, clojure]
---

It's been quite awhile since my last post but I think I have a good reason to
write again considering the interesting times we live in. It's amazing what forced
isolation will inspire in people.

## What is a Social Deduction game?

> A social deduction game is a game in which players attempt to uncover each other’s hidden role or team allegiance.

Source: [Wikipedia](https://en.wikipedia.org/wiki/Social_deduction_game)

I am lucky enough to have worked for two companies (Centro and Grubhub) where employees
started a board game group for fellow enthusiasts to play regularly. For whatever
reason, we would usually gravitate towards social deduction games as our favorite
to play, due to the size of group and interest level of the players.

Some popular social deduction games with the group:
* [Coup](https://boardgamegeek.com/boardgame/131357/coup)
* [One Night Ultimate Werewolf](https://boardgamegeek.com/boardgame/147949/one-night-ultimate-werewolf)
* [Spyfall](https://boardgamegeek.com/boardgame/166384/spyfall)
* [Deception: Murder in Hong Kong](https://boardgamegeek.com/boardgame/156129/deception-murder-hong-kong)
* [Salem 1692](https://boardgamegeek.com/boardgame/175549/salem-1692)

We played these regularly, and many more that are not social deduction games. But by
far the most popular with the group was [The Resistance: Avalon](https://boardgamegeek.com/boardgame/128882/resistance-avalon), which also happens to be the highest rated on Board Game Geek.

We played so much that the setup became cumbersome and we tried to come up with
ways to speed up the game. I decided to create a setup app to ensure speedy and
accurate setup, which I completed almost exactly 4 years ago, on Apr 3, 2016. It
has been used countless times by different groups of friends and colleagues to
play Avalon. The app was written in Clojure on the backend, with ClojureScript, React,
and MaterialUI on the frontend.

Since the recent social distancing mandates due to COVID-19, I have been
unable to play any social deduction games. They are the type of games that don't
translate well to digital format. So I decided to make some updates to be able
to make that happen.

But before we go into that, let's spend a little time learning about the game.

## The Resistance: Avalon

> **The Resistance: Avalon** pits the forces of Good and Evil in a battle to control the future of civilization. Arthur represents the future of Britain, a promise of prosperity and honor, yet hidden among his brave warriors are Mordred's unscrupulous minions. These forces of evil are few in number but have knowledge of each other and remain hidden from all but one of Arthur's servants. Merlin alone knows the agents of evil, but he must speak of this only in riddles. If his true identity is discovered, all will be lost.

Source: [Board Game Geek](https://boardgamegeek.com/boardgame/128882/resistance-avalon)

Like its predecessor, The Resistance, the players are separated into a good team
and evil team, trying to vote to get their teammates on quests and fulfill their
victory conditions. For the good team, most players have little information about the other
players, but they still need to select their teammates for quests. For the evil team,
they know their fellow players, but can't reveal them without risking their
victory.

The setup of the game should take all of the players, separate them into the
right sized team, and give them the information on the other players that they need.
There are many more parts of the game, but the original app was only intended for
setup. The rest of the game involves voting for quest participants, and then having
the participants pass or fail the quests based on their team assignment and/or strategy.

Screenshots of the original version:

<img alt="Start Page" src="/assets/avalon/start.png" class="avalon" />
<img alt="Join Page" src="/assets/avalon/players.png" class="avalon" />
<img alt="Player Information" src="/assets/avalon/mordred.png" class="avalon" />

## The Resistance: Avalon, Social Distancing Edition

The social distancing rules mean we can no longer be in the same room as our friends
while playing the game. However, much of the gameplay involves interacting
with the other players by discussing, voting, and convincing others that you
should be picked for quests. Even though a little bit is lost from in person, most
of these aspects can easily be done over video.

Other aspects of the game are more difficult, specifically going on quests. The
game uses cards with "Success" and "Fail" on them, and they are played in secret.
This was the key new feature I needed to add to support remote play.

So essentially the game is played in these stages:

1. **Setup**: Take in the players names, assign them a role, and give them the information
they need in secret. This was the only thing originally handled by the app.
2. **Team selection**: Pick a number of people at the "table" to go on a quest, and everyone
votes yes or no, simultaneously, in public. A show of hands over video will suffice. This
part also occurs in seated order, which we won't have over video, so the app decides
a virtual seating order.
3. **Quests**: Those chosen players will go on a quest together, choosing "Success" or
"Fail" in secret. The app allows any player to select the players, then allows each
player to submit a "card" as well as revealing the results.

I also wanted to take the opportunity to make some improvements to the UI to help
new players understand what team they are on, and some extra helpful information
about the gameplay.

### End Results

Ultimately I implemented several improvements:

1. Update to the latest and greatest of every library.
2. Make player information collapsible, so they can keep their phone open.
3. Add color hints to help separate good and evil.
4. Add more detailed instructions about the phases of the game.
5. Show a virtual seating order, for remote play.
6. Add a Quest panel along with interactions to go on quests.
7. Create a better domain name than the previous Heroku one.

Here are the resulting screenshots:

<img alt="Play Updated" src="/assets/avalon/play_updated.png" class="avalon" />
<img alt="Quests Updated" src="/assets/avalon/quests_updated.png" class="avalon" />
<img alt="Quest Progress" src="/assets/avalon/quest_progress.png" class="avalon" />
<img alt="Quest Picker" src="/assets/avalon/quest_picker.png" class="avalon" />
<img alt="Quest Card" src="/assets/avalon/quest_card.png" class="avalon" />
<img alt="Quest Waiting" src="/assets/avalon/quest_waiting.png" class="avalon" />
<img alt="Quest Results" src="/assets/avalon/quest_results.png" class="avalon" />

## Try It Out

If you're a fan of The Resistance: Avalon, please give it a try. I'm always happy
to frantically refresh the Google Analytics page and see the traffic increase.

* Play: [merlin.life](http://www.merlin.life)
* Source: [github.com/baritonehands/avalon](https://github.com/baritonehands/avalon)
