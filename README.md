# MDP_concise

## Aim
Given a map of dimensions ~1m-2m with 4-6 obstacles placed on a gridmap, where each obstacle is a cuboid with 4 faces, of which 1 has an image attached to it. Goal of the challenge is to complete the traversal from the start to all the obstacles in the shortest amount of time and accurately identify the id of the images on the obstacles.
## Constraints and conditions
The robot needs to arrive a set distance before the obstacle and have its mounted camera face the image on the obstacle and detect the id of the image before moving on to the next obstacle. Obstacle placement and direction facing is only given to teams 5 minutes before the commencement of the challenge. Ensure that within the 5 minutes of preparation of 4-wheeled robot, the data is accurately input and connections between the robot, tablet and computer running the path finding algorithm are set up. Once preparations are over, robot is supposed to traverse the gridmap according to steps and directions produced by the algorithm given the data of the positions and facings of the obstacles. Every collision with obstacles will result in time penalty for the team.
## Algorithm in brief
Robot movement is similar to a 4-wheeled car, with a turning radius. Upon testing, we can find the grids that are out-of-bounds for the robot. Using that, we can perform Uniform Cost Search from the one point to another point to find the smallest cost incurred. By tracking the parents of each new expansion we are able to trace a path taken as well.
The problem of shortest path for the entire traversal of all obstacles can be broken down into subproblems of finding the shortest distance between 2 points or 2 positions for the robot to id the image. We decided to exhaustively search for the best combination of sequence of images to id to find out the global best path that should be taken.

## TLDR
- UCS to solve distance between 2 points
- Exhaustive search to solve total travelled distance
