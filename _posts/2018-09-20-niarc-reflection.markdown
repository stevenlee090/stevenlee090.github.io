---
title: "NIARC Post-final Reflection"
layout: post
date: 2018-07-30 08:00
image: # /assets/images/iterm.png
headerImage: false
tag:
- national instrument
- autonomous
- robotics
- competition
- development
- control systems
- lidar
- sensors
star: false
category: blog
author: stevenlee
description: NIARC post-final blog post, detailing the event and experience.
---

<iframe width="854" height="480" src="https://www.youtube.com/embed/JphykMqKYzc?ecver=1" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<figcaption class="caption">Quarter Final Round - University of Melbourne vs University of Auckland (Speedy Kiwi)</figcaption>

---

## Deliverables and Outcome Summary
* Completed all 6 milestones
* Competed in final competition with participants from Asia Pacific region (16 teams in total)
* Placed second overall
* Stressful, challenging but rewarding experience.

## Day 0 - Final touch-up for development

Over the final weekend before the final, two team members and the mentor was able to get together to finish up the main algorithms and coding for obstacle avoidance. The robot was then tested on a scaled down version of the track built within a 2-car-space garage.

---

![Garage](/assets/images/niarc_final/garage.jpg)
<figcaption class="caption">Test Track in Garage</figcaption>

---

Even though the time was short, we were able to improve and develop upon the obstacle avoidance algorithms which will ultimately be used in the final NIARC event. However, there were still some areas which were overlooked and will not be realised until Day 1. This includes the lack of testing in a large and empty area which simulates the actual race condition, and also forgetting to check the actual gap/distance between the red tape and the ramp which also affects how the robot reacts to the ramp terrain element. These miscalculations will eventually come back to haunt us when the actual event kicks off in Sydney.

The day ended rather late as we continued tuning into the night, ensuring that the robot is capable of performing the required tasks both on the outer track and inner track. We mainly tested the robot on the outer track and then translated the improvements and changes to the inner track afterwards. Although the robot was not performing perfectly, we were still optimistic that we had a decent chance against other competitors.

## Day 1 - Tuning in Sydney 
The day started early as we had to make it to the airport to catch the flight scheduled for 8:50am. Due to the slight delay in takeoff, we were able to do some Labview coding for the finite state machine and revamp the image processing parsing. After touch-down, we took the train from Sydney Airport to Central Station and made our way to the Great Hall of UTS (University of Technology Sydney).

Upon arrival at noon, majority of the other teams were already setup and started testing on various elements of the track. We immediately unpacked the robot and began our own calibration/testing, and this is where many issues arose.

---

![Great Hall 2](/assets/images/niarc_final/great_hall2.jpg)
<figcaption class="caption">Great Hall - University of Technology Sydney</figcaption>

---

During testing, the robot would sometimes drift off the track due the the vastly different measurements collected by the LIDAR sensor in this bigger open space area. This prompted us to adjust how the robot would index and use the LIDAR data to perform wall tracking. However, this was still not enough to ensure good robustness, so we eventually decided to slow down the robot to make sure that the robot would not drift away from the track while cornering at reasonable speed.

We followed the same strategy of testing and refining the outer track first, then moved on to the inner track. During inner track tuning, we realised that the inner track would not suffer from the aforementioned problem of drifting off the track, and it became evident that running our robot on the inner track will provide us with the most advantages and consequently the highest possible score.

Due to inconsistent lighting conditions provided by the officials, the tuning session for Day 1 was extended from 6:00pm to 6:30pm. The inconsistency of the lighting in the room and from the projector proved to be a huge challenge for many teams as most robots relied on computer vision and image processing in one way or another.

---

![UTS Robot](/assets/images/niarc_final/uts_bot1.jpg)
<figcaption class="caption">RobUTS? - University of Technology Sydney Team</figcaption>

---

Near the end of the day, our robot exhibited some unexpected error as it finishes the ramp section. For some unknown reason, it would spin in circle at the same spot, and this problem repeated a few times and perplexed everyone as we were unable to find the root cause of this behaviour. Also real-time debugging on Labview was more difficult than usual as there were numerous WiFi devices broadcasting and receiving data at the same time. The countermeasure was to revert back some of the parameter changes we made to the robot during, in the hopes that this would stop this erratic behaviour from happening.

At the end of Day 1’s tuning session, we packed up our luggage and proceeded to check-in at designated hotel. After the bags were dropped off, we made our way to a nearby Japanese restaurant for some ramen and then picked up some [delicious but risky strawberries](http://www.abc.net.au/news/2018-09-14/strawberry-needle-scare-what-you-need-to-know/10248736).


## Day 2 - NIARC Final Event

Since we were given a final tuning session from 7:30am to 8:00am, we woke up early, ate some breakfast and then quickly checked out of the hotel and made our way back to the event venue to setup and tune our robot.

Structure of the competition:
* Qualifiers (4 heats)
* Round of 16 (knockout)
* Quarter Finals (2 heats)
* Semi Finals (2 heats)

### Qualifiers

The first round of event was the qualifiers stage, where teams are placed in 4 groups, with each groups having 4 teams. Each team is given the opportunity to run 4 heats (2 runs on the outer track, 2 runs on the inner track) and the best score is used to for ranking purposes.

The group we were assigned to was Group B, and it was arguably one of the most competitive groups out of all. This is because RobUTS and Speedy Kiwi both had robots which were fast, robust and really well refined.

---

Qualifiers - Group B Participants:

* University of Auckland (Speedy Kiwi)
* University of Melbourne (Team A)
* University of Technology Sydney (RobUTS?)
* University of Waikato (Team W)

---

We ended up ranking third in the qualifiers group, with the top 3 scores being extremely close to each other.

It is rather unfortunate to see that many of the teams which relied mainly on computer vision were unable to run their robot. If those computer vision based robots were able to run like they did the previous day, the event would definitely be more exciting.

### Round of 16

The following round of 16 were much less forgiving as it consisted of pure knockout rounds, so the teams only had one chance for the track they were assigned to. Before the rounds began, the judge would call up representatives from the competing teams, and the team which guesses the correct coin toss would choose their desired track (outer or inner).

---

![Team W](/assets/images/niarc_final/team_w.jpg)
<figcaption class="caption">Team W Robot - University of Waikato</figcaption>

---

We were rather lucky in a way that even though our robot had problems with colour detection, the opposing team (Team W from University of Waikato) did not make it far into the track, so we were able to scrape pass this round.

### Quarter Finals

The proceeding round would become one of the most intense rounds ever, as we were paired with Speedy Kiwi from University of Auckland. Part of the quarter final event is presented in the YouTube video at the beginning of the post.

---

![Speedy Kiwi](/assets/images/niarc_final/speedy_kiwi_2.jpg)
<figcaption class="caption">Speedy Kiwi - University of Auckland</figcaption>

---

Shortly before the results came out, we prepared ourselves for the worst as Speedy Kiwi was such a formidable opponent. The opponent's robot was fast, robust and really well refined. Both teams had perfect runs on the inner track and the judges took almost 30 minutes to finalise the results for the quarter finals because they were so close.

* University of Auckland - Speedy Kiwi: 1053.6
* University of Melbourne: 1060.2

---

![Quarter Final Results](/assets/images/niarc_final/quarter_final_score.jpg)
<figcaption class="caption">Quarter Final Results</figcaption>

---

### Semi Finals

At this point, we were completely speechless, as we were guaranteed a second place already and just need to place the final round against Victoria University of Wellington. However, this is also where things turned to the worst, thanks for [Murphy’s law](https://en.wikipedia.org/wiki/Murphy%27s_law). One of our team member accidentally tripped over the track divider, dropping our robot onto the ground. For some miraculous reasons, the robot survived the drop and we were still able to compete in the final rounds of the day.

---

![Battle Scar](/assets/images/niarc_final/battle_scar.jpg)
<figcaption class="caption">Battle Scar After Drop</figcaption>

---

For the outer track run, the robot almost made its way to the finish line without issues, but then decided it would drift away from the track at the final corner before the finish zone. For the inner track run, even though the robot was much faster than the competing robot, it knocked over an obstacle after the first zig-zag, and it also missed a zig-zag over the second yellow/black-taped zone.

This resulted in point deductions for both runs, placing our scores slightly lower than the opponent, hence losing the championship round to VuW (Victoria University of Wellington). It is important to acknowledge that even though VuW’s robot is much slower than our robot, it was amazingly consistent, and was able to perform all the required tasks over every single terrain elements, while avoiding all the obstacles placed along the track.

---

![Robot Group Photo](/assets/images/niarc_final/all_bots_2.jpg)
<figcaption class="caption">Robots Group Photo</figcaption>

---

In the end, we were more than satisfied with the outcome of the competition. We are very grateful for all the help and support from our mentors, **Tony** and **Neo**, and our sponsors **SICK Australia** and **Melbourne School of Engineering**. Without them, it would have been impossible for us to be where we are today and we look forward to improving and creating better robots in the future.

---

![Group Photo](/assets/images/niarc_final/group.jpg)
<figcaption class="caption">University of Melbourne NIARC Team</figcaption>

---

I would also like to thank all the team members **Ammar, Grant, Howard, Jeremy, Heraldo, Andrew, David** for their hard work and contributions to the project this year. From CAD design, to laser-cutting, 3D printing, to software and hardware implementation, I hope that everyone had fun and learnt something in the process.

---

![Trophy](/assets/images/niarc_final/trophy2.jpg)
<figcaption class="caption">Jeremy with our trophy</figcaption>

---

## NIARC 2018 Things Learnt

The enumerated list below contains some of the key areas which can be improved for future NIARC teams.

1. Use a router for myRIO connection.
2. Use interrupts and proper event handling.
3. Controllable LED lighting for colour sensing. Ring lighting if possible.
4. More debugging outputs, for visual debugging.
5. Learn to program properly, asynchronous loops and race conditions.
6. Optionally, could write your own PID for better debugging and understanding.
7. RGB led debugging to show which state it is in right now. Allows faster and more visual debugging.
8. Wall tracking speed control, can use linear regression and use the error to control speed
9. Take Uber instead of using opal card, it is basically one third the cost.
10. **Slow and steady wins the race. Taking Victoria University of Wellington’s approach, it can be hugely beneficial to prioritise robustness and reliability over speed.**

---

![Sick Bot](/assets/images/niarc_final/sick_bot1.jpg)
<figcaption class="caption">Robot Tuning in Progress</figcaption>

---

_Photography by David Liao and Steven Lee._
