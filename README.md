# Behavior Planner
Behavior Planner contains a FSM representing maneuvers and transitions between them, a cost function used to choose the best next state for the ego car.

It's a quiz in Udacity Self-Driving Car Program. Comments are littered across the files to explain how things work.
1. `road` represents the entire road environment containing all the cars. It can update itself once at a time step
2. The process of updating is
    1. generate future trajectories for all the surrounding cars
    2. generate all possible next states for the ego car
    3. compute cost for all possible next states and choose the one with lowest cost
    4. generate trajectory according to the chosen state
    5. update the attributes like velocity or acceleration for all the cars

Note in practice the maneuvers are the real product of behavior planning module. The real trajectory of the ego car is generated based on that using a trajectory generator. Given a fixed set of maneuvers (a chosen state), often there are a set of trajectories in which you need to pick one according to a cost function (not the same one you use in behavior planning module).
