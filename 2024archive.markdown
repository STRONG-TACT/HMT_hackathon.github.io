---
title: 2024 Dice Adventure Competition
nav_title: 2024
permalink: /2024_competition/
layout: page
order: 5
---

The 2024 competition has been concluded. We thank all participants for attending and playing our game!

[2024 Hackathon](hackathon.markdown) \\
[2024 Competition Report](https://drive.google.com/file/d/15CsFjjArwBT6RsKYwW_ueI5S73PHRWU9/view?usp=sharing)

> 📢 News! <br>
> July 28 --- 🙏Thank you all for your participation! The 2024 Dice Adventure Competition has came to an end. Winners will be announced on our website in early August. \\
<!-- > Join us on [Slack](https://join.slack.com/t/dice-adventure/shared_invite/zt-2ia9cgtkn-VAKxgzLBYlS9tzKWmE8ePA) channel for most up-to-date information. \\ -->
<!-- > ~~Daily virtual match making session available at **8am - 10am EST, 12pm-2pm EST, 8pm - 10pm EST** from **July 16, 2024** to **July 27, 2024**. [Sign up](https://gatech.co1.qualtrics.com/jfe/form/SV_bqqsRdimotXh8nI) to [compete](https://cmu-tact.itch.io/dice-adventure)!~~ \\
> ~~June 25 --- Agent submission deadline has been extended to July 7.~~ \\
> ~~May 8 --- Dice Adventure is online! See [Game](/game) for more details.~~ \\
> ~~May 1 --- The agent submission portal is open! See [Submission](submission.markdown) for details.~~ -->


|[Submit an Agent](/submission/) 🤖       |[Play Online](/play/) 🌐         |[Play In Person](/hackathon/) 🎲       |
|----------------------|---------------------|----------------------|
|Design, develop and train AI agents that can play the game.                |Play the game online at multiple virtual match-making event.                 |Sign up for the in-person hackathon and play the game in person.                  |



* TOC
{:toc}



Welcome to the first Dice Adventure Human-AI Teaming Competition! We are selected as one of the game-AI competitions hosted at 2024 [Conference on Games](https://2024.ieee-cog.org/). In this competition, we are using an in-house developed game called Dice Adventure as the environment and encourage participants to explore human-AI teaming effects. Dice Adventure is a multi-player turn-based dungeon crawling game that takes three players to play. Detailed information on game rules, game tutorial and frequently asked questions can be found at [Game](game.markdown) page.

We offer two tracks and welcome participantas at all levels. To participate, you must sign up for one or both track(s). If you are interested in developing an agent, please check out the guidelines in [Submit AI](submission.markdown) page for *agent development track*. The starter code and training environment can be accessed at the [Dice-Adventure-Agents](https://github.com/STRONG-TACT/Dice-Adventure-Agents) repo on GitHub. If you do not wish to submit an agent but are still interested in this competition, please check out the details on the [Play](/play/) page for signing up as a player in the *player track*. We will be hosting a few virtual and in-person match-making events to bring players together.

As part of the match-making events, we will be hosting an in-person hackathon event at Georgia Institute of Technology in Atlanta, GA in the United States. The hackathon is a free event that welcomes students, researchers, developers and anyone interested in our game and competition to get together. We will be organizing a series of tutorial sessions, interactive demos, working sessions and game tournaments during the two-day event. RSVP information, event schedule and accommodation suggestions can be found at the [Hackathon](/hackathon/) page.

The following video provides an overview to the competition tracks, rules, short game tutorial and information on setting up the training environment. We hope to bring exciting experiences to the participants and exploring critical human-AI teaming questions to gain a better understanding in team communication, coordination, and adaptation.

<!-- TODO
- hackathon info
- scoring function -->


<iframe width="640" height="360" src="https://www.youtube.com/embed/cvV_hTAYgy4?si=qu2tJ5bUwP8vhw-x" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<!-- [![Watch the video](/files/timeline.png)](https://www.youtube.com/watch?v=cvV_hTAYgy4) -->
<!-- https://www.dropbox.com/request/5Fnu21FIHgVk9pnTmxId -->


## Key Dates

| Key Dates<br/>All deadlines are 11:59pm UTC-12:00 (anywhere on Earth) |                     |
|---------------------------------------------------|---------------------|
|~~Release agent training environment~~                 |~~March 15, 2024~~       |
|~~Release low fidelity version of Dice Adventure~~     |~~March 15, 2024~~       |
|~~Release a playable version of the game~~             |~~March 15, 2024~~       |
|~~Release game tutorial~~                              |~~March 15, 2024~~       |
|~~[CoG auxiliary paper](https://2024.ieee-cog.org/call-proposals/#cfp) submission deadline~~                |~~Apr 28, 2024~~             |
|~~Release game play demo videos~~                      |~~May 1, 2024~~          |
|~~Release leaderboard design~~                         |~~May 1, 2024~~          |
|~~Release evaluation criteria~~                        |~~May 1, 2024~~          |
|~~Release Fully functional game~~                      |~~May 8, 2024~~          |
|~~Release game with AI interface~~                     |~~June 15, 2024~~        |
|~~Hackathon signup ends~~                              |~~June 24, 2024~~        |
|~~Dice Adventure Hackathon~~                           |~~June 24-25, 2024~~     |
|~~Agent submission portal closes~~                     |~~July 7, 2024~~         |
|~~Online participation starts~~                        |~~July 16, 2024~~        |
|~~Online participation ends~~                          |~~July 27, 2024~~        |
|~~Winners announced on website~~                       |~~Early August, 2024~~   |
|~~Conference on Games~~                                |~~August 5-8, 2024~~     |


## Evaluation Criteria

As the goal of the competition is to better understand human-AI teaming dynamics, the submitted agents will not be evaluated by running against benchmarks or through bot fight. All the agents will be selected at least once and play with players in the player track as a team. Below are the scoring function showing how a team score is calculated. The score consists of a base score with a decaying factor and bonuses for each character. For each level, each character gets a bonous of 10 and they lose the bonus proportional to losing the health. If a character lose all the health in a level, it will not be eligible for the bonus.

<img src="https://latex.codecogs.com/svg.latex?\Large&space;S_i = 100 \times d^{r_i} + \sum_{j=1}^{3} \frac{h_{ij}}{h\_max_{ij}} \times rs_{ij} \times 10" title="\Large S_i = 100 \times d^{r_i} + \sum_{j=1}^{3} \frac{h_{ij}}{h\_max_{ij}} \times rs_{ij} \times 10"/>

<img src="https://latex.codecogs.com/svg.latex?\Large&space;team\_score = \sum_{i=1}^{n}S_i" title="\Large team\_score = \sum_{i=1}^{n}S_i"/>

- d: decaying factor, we are using d=0.95 for competitions
- i: the current level the team is at
- j=(1, 2, 3) representing each of the three characters
- r: the number of rounds the team took to clear a level
- rs: if a character lose all lives (rs=0) in a level 
- h: the health a character remains
- h_max: the maximum health a character has
- n: the total number of levels the team has cleard


## Prizes

Our competition is sponsored by the IEEE Computational Intelligence Society Education Competition Fund with a total cash prize of **$1,000 USD**, which will be awarded to participating teams ranking at the top three places on the [leaderboard](leaderboard.markdown). The prize will be equally distributed among team members --- human players and agent developers of agents. Below is the distribution of prizes:

🥇 1st place - $500 USD<br>
🥈 2nd place - $300 USD<br>
🥉 3rd place - $200 USD<br>

We congratualtes the following winners! 🎉

🥇 1st place - Leon Lange<br>
🥈 2nd place - Keyang Zheng<br>
🥉 3rd place - Amira Beck<br>

Note: the other two players on each of the winning team were either a baseline agent or a human player that was inelegible for the prizes.



## Form and Links

Player track signup form: [https://gatech.co1.qualtrics.com/jfe/form/SV_bqqsRdimotXh8nI
](https://gatech.co1.qualtrics.com/jfe/form/SV_bqqsRdimotXh8nI
)\\
~~Hackathon signup form:[https://gatech.co1.qualtrics.com/jfe/form/SV_cBkazbWRdGRW9y6](https://gatech.co1.qualtrics.com/jfe/form/SV_cBkazbWRdGRW9y6)~~ \\
~~Agent submission form: [https://gatech.co1.qualtrics.com/jfe/form/SV_6Qd51ZHWarDyzu6](https://gatech.co1.qualtrics.com/jfe/form/SV_6Qd51ZHWarDyzu6)~~ \\
~~Agent file submission link: [https://www.dropbox.com/request/5Fnu21FIHgVk9pnTmxId](https://www.dropbox.com/request/5Fnu21FIHgVk9pnTmxId)~~


## Organizers
Qiao Zhang, [qzhang490@gatech.edu](qzhang490@gatech.edu) \\
Glen Smith, [glensmith@gatech.edu](glensmith@gatech.edu) \\
Varun Girdhar, [vgirdhar@andrew.cmu.edu](vgirdhar@andrew.cmu.edu) \\
Yuxuan Dong, [yuxuando@andrew.cmu.edu](yuxuando@andrew.cmu.edu) \\
Ziyu Li, [ziyul@andrew.cmu.edu](ziyul@andrew.cmu.edu) \\
Erik Harpstead, [harpstead@cmu.edu](harpstead@cmu.edu) \\
Christopher J. MacLellan, [cmaclellan3@gatech.edu](cmaclellan3@gatech.edu)

Last updated on January 19, 2024.

<!-- Dice Adventure is a multi-player, turn-based, dungeon crawling adventure game developed at Carnegie Mellon University. This is the first time for us to host the Dice Adventure Human-AI teaming competition. There are two tracks of the competition - (1) participants can submit their agents to the agent track;  (2) participants can play with other players and submitted agents in the player track. Agents submitted to the agent track will play with players in the player track and be evaluated on the team score they achieved after running multiple levels of games. Winners will be declared based on overall teaming performance. We hope to bring exciting experiences to the participants as well as exploring critical human-AI teaming questions and gain a better understanding in team communication, coordination and adaptation. An introduction of the competition can be found in [this video](https://www.youtube.com/watch?v=cvV_hTAYgy4). -->
