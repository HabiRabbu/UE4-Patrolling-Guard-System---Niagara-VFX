# Advanced AI Guard System for Game Environments

## Project Overview
This project focuses on creating a dynamic and realistic AI guard system suitable for game environments. The guard is designed to patrol, guard, and chase based on specific conditions and triggers, enhancing player experience and interactions.

## Guard Behaviors:
*Patrolling: The guard moves along a predefined path.
*Guarding: Guard stands guard over an object in the environment.
*Chasing: Guard chases the player if they come into its line of sight.

## States Implementation:
The behaviors are based on three states:

*Patrol
*Guard
*Chase

These states are defined as enumerators in the game logic.

### Logic Breakdown:
*Initiating states at the game's start.
*Executing states based on game conditions and triggers.

### At Begin Play:
The enemy starts patrolling along the pre-defined path objects in the environment. These paths are saved to a local array. After this, the patrol state is initiated, allowing the guard to move between the points.

### State Transition Logic:
Logic is in place to toggle between patrol and guard states, with conditions set to initiate the chase state. Conditional initiators like “On Hit” and “On See Pawn” play a crucial role here.

*On See Pawn: Stops the current state and movement, initiating the chase state at intervals of 0.1 seconds. This ensures the guard maintains a chase if the player is in sight and has a responsive rate if the player goes out of view.

*On Hit: If the guard's shield is hit (e.g., by a player's bullet), the guard's reaction depends on its current state. If the guard sees the player, it initiates a chase. Otherwise, it rotates towards the player's last known location.

### State-specific Logic:
*Guard State: The AI moves to a specific guard location (e.g., a cylinder representing loot) and adopts a random rotation.
*Patrol State: The guard moves between patrol points based on an index. A random delay is incorporated between each point transition.
*Chase State: The guard's speed increases, and it moves towards the player's last known location. If the player is out of sight, the guard waits momentarily before reverting to its previous state.

## Behaviours:
*Patrol Mode: When patrolling, the guard is oblivious to the player if out of its sight.
*Chase Mode: As soon as the player is in its line of sight, the chase is on!
*On Hit Effect: A Niagara VFX is instantiated when the guard's shield is hit, signaling the guard to initiate a chase.

## Conclusion:
This advanced AI system for guards enhances the gameplay experience by introducing dynamic reactions based on player actions and environmental conditions. Explore the code to delve deeper into the logic and the system's intricacies.
