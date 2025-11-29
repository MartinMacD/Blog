---
layout: default
title: "Traffic Models"
date: 2025-11-28
categories: [projects]
permalink: /projects/traffic-models/
---
# Traffic models
During the undertaking of my honours project, which is based on creating a 3D continuous flying car model, I explored some existing traffic models to better understand how they function.
## BML traffic model ([source](https://github.com/MartinMacD/BML-Traffic-Model))
The original paper this model is based on is: _Biham, O. et al. (1992) Self Organization and a Dynamical Transition in Traffic Flow Models_.

### About
In this traffic model, east-bound cars (red) attempt to move east while south-bound cars (blue) attempt to move south. If the cell a car is attempting to move into is free, they move into that cell, if it is not free, they remain in their current cell. 
<br> 
The grid is a torus, meaning cars wrap around once they reach the edge of the screen. 

### Goal
The goal of this model is to observe basic traffic patterns and visualise how traffic flow is dependant on car density.


### Examples

Car density of 0.6 which quickly descends into gridlock.
<img src="/assets/images/bml_sim_gridlock.gif" alt="BML sim at gridlock capacity" title="BML sim at gridlock capacity" class="responsive-img">
<hr class="container-hr">

Car density of 0.3 which allows for free flowing traffic.
<img src="/assets/images/bml_sim_low_density.gif" alt="BML sim at low capacity" title="BML sim at low capacity" class="responsive-img">

<hr class="container-hr">
## Nagel-Schreckenberg model ([source](https://github.com/MartinMacD/Nagel-Schreckenberg-Traffic-Model))
The original paper this model is based on is: _Kai Nagel, Michael Schreckenberg. (1992) A cellular automaton model for freeway traffic_.

### About
In this traffic model, a single-track, circular motorway exists with cars that populate it. Each car has a velocity and will move that many cells forward per simulation step. If a car encounters another car, it will slow down to avoid crashing into it. There is an element of random slowdown which can affect individual cars at each step of the simulation which adds unpredictability.

### Goal
The goal of this model is to observe how traffic jams and congestion patterns emerge based on traffic density and driver unpredictability.

### Examples
Starting from the top, cars move right.

X-Axis - Position on the road. Y-Axis - Time.
<hr class="container-hr">
Parameters: Length = 40, density = 0.3, max_velocity = 5, probability_of_slowdown = 0.3, steps = 40, seed = None.
<br>
<br>
Semi-free flowing with occasional slowdown.
<br>
<br>
`............0340.53..0.3......0.02...5......0.15..
..5.........0000.0..20.....4...10...3....4..0.0...
.......5....000.1.1.0.1.......30.1......4..20.0...
...........400.10..1.1.1......00...2......20.1.1..
...........00.100...1.1..2....0.1....2....0.10...2
..3........00.00.1...1..2...3..1.1.....2..0.0.1...
......4....0.100...2...2...3..20...2....1..1.1..2.
.3........4.100.1....2...2..1.0.1.....3...20...2..
3....4.....100.1..2....2...2.1.1..2......30.1.....
....4.....500.1..2..2....2..1.1..2...3...0.1.1....
.........5000...2.1...2....2.1..2..2...2..1.1.1...
.........0000....1..2....3..1..2..2..2...20.0..1..
.........0000.....1...2...1..1...2..2...30.1.1...2
.2.......0000.......2....3.1..1....2...300..1..2..
....3....000.1.........3..1..2..2.....300.1..1...2
..3.....400.1..2.........2..2..2..2...00.1..2.1...
......4.000..1....3.......1...2..2..2.0.1..20..1..
......0.00.1..1.......4.....2..1...20..1.1.0.1...2
..3....10.1.1...2..........5..2..2.00..0..1.1..2..
3.....40.1.1.1.....3.........2.1.0.00...1..1.1....
...3..0.1.1.1..2.......4......1.1.10.1....20...2..
3....20..1.1..2...3.........5.0.0.00..1...0.1.....
....400..0...2..2.....4.....0.0..100....2..1..2...
....00.1..1...1....3......4.0..1.000.....1...2...3
...40.1..2.1....2......4..0.0...100.1......2....3.
..40.1..2.1.1......3.....2.1.1..00.1..2......2....
..0.1.1..10...2.......3..0..1.1.0.1.1....3......3.
.3.1.1..200......3......2.1..1.1.10...2......4....
.0.0...200.1.........4...1..20..10.1.....3.......4
1.1.1..00.1..2.........2...20.1.0.1..2.......4....
.10...20.1..2..2.........2.0.1.1.1.1...2........3.
20.1..0.1.1..1...2.......0..1.1.1.1..2...2........
0.1.1..10...2..2....3.....1.0..10...2...3..2......
.1.1..200.....2...3....3..0..1.0.1.....3..2...3...
4.1..200.1.......3....4..2.1..1.1..2....1...2.....
.1..2000...2.........4.1.0...2.1.1....3...2....3..
...2000.1.....3.......10..1...1.1..2.....3...3...2
.2.000.1.1........4...0.1...2.0..1....3.....3...3.
2.1000..1..2.........30..1...1.1...2......4....3..
.1000.1...2...3......0.1...2.0...2....3.......4.1.`
<hr class="container-hr">
Parameters: Length = 40, density = 0.5, max_velocity = 5, probability_of_slowdown = 0.3, steps = 40, seed = None.
<br>
<br>
Much more prone to jams forming with overall slower car speed.
<br>
<br>
`..1145402.30...3.4513.00.5..2304...44...0.....1...
..000000.10.1...1000.10.1..2000..2.0...30.......2.
.300000.100..1..000.10.1..2000.1.0..1..0.1........
.00000.100.1...2000.0.1..2000.1.1.1..1.0..1.......
.0000.1000..1..0000.0...2000.1.1.1..2.1.1..1......
.000.1000.1...20000..1..000.10..1..20..1..2..2....
.00.1000.1..2.0000.1...200.10.1...20.1...2..2..2..
30.1000.1.1..1000.1..2.000.0.1..2.0.1.1....2.1....
0.10000..1.1.0000...20.00.1.1..20..1.1.1...0..1...
0.00000..0.0.0000...00.0.10...200...1.1..2..1..1..
0.0000.1..10.0000...0.10.0.1..000....1..2..2..2..2
.1000.1.1.00.000.1...10.1.1..200.1.....2.1...2.1.0
1000.1.1.10.100.1..2.0.1.1..200.1..2....1..2..10..
000.10..10.100.1.1..10..1..200.1..2...3..1..1.0.1.
00.10.1.00.000..1..20.1..1.00.1..2...3..2..2.10..1
00.00..10.100.1...20.1..2.10.1..2...3..2..2.10.1.0
0.100..0.100.1.1..0.1..20.0.1..2..2..1..1.0.0.1.10
.1000...100.1.1.1..1..20.1.1.1...2..2..20..1.1.100
1000.1..00.10..1..2.1.00..1.1..2...2.1.0.1.0..100.
0000...20.10.1...2.1.10.1..1.1....3.1.10.0..1.00.1
000.1..0.10.1..2..1.10.1..20...2..0.0.0.1.1..100.0
00.1.1..10.1..2..20.0.1..200.....20.0..1.1.1.00.10
00..1..20.1..2..20.1.1..2000.....0.1.1..1.1.10.100
00...1.00...2..200.0...2000.1.....10...2.1.10.1000
0.1...10.1....200.1.1..000.1.1....0.1...10.0.10000
.1.1..0.1..2..00.10...200.1.1..2..0..1..00..100000
..1.1.0..1..1.0.10.1..000..1.1...20....20.1.000000
1..1.1.1..1.0..10.1..200.1.0..1..0.1...0.1.100000.
..2.10..1.0.0..0.1.1.00.10.0...1..1.1...1.100000.1
1.0.0.1..1.10...1.10.0.10.1.1....20...2.0.000000..
0..1.1..2.10.1..0.0.1.10.1.1.1...00....1.100000.1.
.1..1..2.10.1..2.10..100..1.1..2.00.....100000.10.
...2..2.100...2.10.1.00.1.0...20.0.1....00000.100.
....1.0.00.1...10.1.10.10..1..0.1.1..2..0000.100.1
.2...1.10.1.1..0.10.0.100...1..1.1..2..2000.1000..
....3.100..1..20.0.1.100.1...1.0...2..2000.10000..
.....100.1..1.0.1.1.100.1.1..0..1....20000.0000.1.
.....00.1..20.0..1.100.1.1.1.0....2..0000.10000..1
.2...0.1.1.0.1.1..1000..10..10......2000.10000.1..
...2..1.1.1.1.1..2000.1.0.1.0.1.....000.10000.1..2`