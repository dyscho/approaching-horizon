# Approaching Horizon #
A Minecraft datapack that implements a custom gamemode for servers that incrementally decreases the size of the world border. The original idea was inspired in part by [the WoodworksExperiment "Closed Map" concept](https://www.youtube.com/watch?v=OfZ0kgiousA)

## Hypothesis ##
Initially, player interaction may improve by encouraging bartering due to lack of natural resources and discouraging players from moving too far from the world spawn. However, as the world border gets smaller, what few resources remain may be fought over and players may opt to escape to the nether instead (if enabled/unmodified)

## Usage ##
Once added to a world, the load function will set the world border to the appropriate starting size (64² chunks) and subsequent calls of some function in-game by an operator will decrement that size (to 48², 32², 16², and 8²). Each resize operation takes place over 3,600 seconds (1 hour), giving players just enough time to relocate. In addition, as the world border becomes smaller, the amount of damage it does to players increases exponentially. Deaths from world border damage are irreversible (players become spectators as in hardcore, until the next iteration).

The current size of the world border is kept track by an internal scoreboard, and when it reaches the minimum value the server becomes hardcore and the objective is to be the last player standing (given their advanced preparation, this process should generally happen very rapidly).

This gamemode is suggested for SMP Minecraft servers with upwards of 20 players.