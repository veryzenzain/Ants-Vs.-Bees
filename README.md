# Ants-Vs.-Bees
A tower defense game called Ants Vs. Bees. As the ant queen, you populate your colony with the bravest ants you can muster. Your ants must protect their queen from the evil bees that invade your territory. Irritate the bees enough by throwing leaves at them, and they will be vanquished. Fail to pester the airborne intruders adequately, and your queen will succumb to the bees' wrath. This game is inspired by PopCap Games' Plants Vs. Zombies.

![splash](https://github.com/veryzenzain/Ants-Vs.-Bees/assets/24355252/1c187e8e-52b9-4b17-9d27-0044f4febff8)


## Core concepts:


The Colony: This is where the game takes place. The colony consists of several Places that are chained together to form a tunnel where bees can travel through. The colony also has some quantity of food which can be expended in order to place an ant in a tunnel.

Places: A place links to another place to form a tunnel. The player can put a single ant into each place. However, there can be many bees in a single place.

The Hive: This is the place where bees originate. Bees exit the beehive to enter the ant colony.

Ants: Players place an ant into the colony by selecting from the available ant types at the top of the screen. Each type of ant takes a different action and requires a different amount of colony food to place. The two most basic ant types are the HarvesterAnt, which adds one food to the colony during each turn, and the ThrowerAnt, which throws a leaf at a bee each turn. You will be implementing many more!

Bees: In this game, bees are the antagonistic forces that the player must defend the ant colony from. Each turn, a bee either advances to the next place in the tunnel if no ant is in its way, or it stings the ant in its way. Bees win when at least one bee reaches the end of a tunnel.

![gui_explanation](https://github.com/veryzenzain/Ants-Vs.-Bees/assets/24355252/ea40f9f0-0519-4d10-b5d5-6fcc0f162778)

## Core classes:


The concepts described above each have a corresponding class that encapsulates the logic for that concept. Here is a summary of the main classes involved in this game:

GameState: Represents the colony and some state information about the game, including how much food is available, how much time has elapsed, where the AntHomeBase is, and all the Places in the game.

Place: Represents a single place that holds insects. At most one Ant can be in a single place, but there can be many Bees in a single place. Place objects have an exit to the left and an entrance to the right, which are also places. Bees travel through a tunnel by moving to a Place's exit.

Hive: Represents the place where Bees start out (on the right of the tunnel).

AntHomeBase: Represents the place Ants are defending (on the left of the tunnel). If Bees get here, they win :(

Insect: A superclass for Ant and Bee. All insects have health attribute, representing their remaining health, and a place attribute, representing the Place where they are currently located. Each turn, every active Insect in the game performs its action.

Ant: Represents ants. Each Ant subclass has special attributes or a special action that distinguish it from other Ant types. For example, a HarvesterAnt gets food for the colony and a ThrowerAnt attacks Bees. Each ant type also has a food_cost attribute that indicates how much it costs to deploy one unit of that type of ant.

Bee: Represents bees. Each turn, a bee either moves to the exit of its current Place if the Place is not blocked by an ant, or stings the ant occupying its same Place.
