---
title: "Path Planning Using C Programming Language"
layout: post
date: 2016-05-23 20:00
tag:
- C
- Programming
- Path Planning
- Path Finding
image: # /assets/images/ddf1.jpg
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "Path planning project using C programming language."
category: project
author: stevenlee
externalLink: false
---

During my first programming subject, Engineering Computation, in university (taken during 2016 Semester 1), the second assignment was focused on a path planning project using C programming language.

I found this project interesting because it actually seems like something which would be useful in real life, since we are constantly using path planning algorithms for GPS navigation and maximising efficiency by finding the shortest possible route.

For the actual implementation of the project, please [click here](https://github.com/stevenlee090/path-planning). The github repository also goes over the example input and example output in more detail under the 'read me' section.

---
### Example Input
```
#####.###.#####
#.....#.#.....#
#.###.#.#####.#
#.#...#.......#
#...#########.#
###.#.........#
#.#.#.#########
#.....#.......#
#.#####.#####.#
#.....#.......#
#####.#########
```

### Example Output
```
Stage 4
=======
maze solution
##########00######  ##########
##        ..##  ##          ##
##  ######02##  ##########  ##
##  ##..04..##              ##
##    06##################  ##
######..##                  ##
##  ##08##  ##################
##..10..    ##--------------##
##12##########--##########--##
##..14..16..##--------------##
##########18##################
```
---

After this subject, I would eventually learn more about algorithms and data structures in the following semester (2016 Semester 2). Within the follow-up course, I learnt about the about graphs, and graph traversal algorithms such as [Dijkstra's Algorithm](https://en.wikipedia.org/wiki/Dijkstra's_algorithm) and how they are applied.

Upon reflecting on this experience, I would like to thank my professor, [Alistair Moffat](http://people.eng.unimelb.edu.au/ammoffat/), who was always passionate about sharing his knowledge and expertise in C programming. His lectures and [textbook](http://people.eng.unimelb.edu.au/ammoffat/ppsaa/) were engaging and enjoyable, I would  recommend checking out the textbook if you are a programmer and would like to learn more about C programming (entry-level).

I sincerely believe that a person's learning experience is highly dependent on the teacher and learning environment. When people interact with passionate and knowledgeable staff members, they are usually more likely to pay attention and engage with the class. However, it is still up to each individual student to decide whether they would like to invest their personal time to learn and master the contents.
