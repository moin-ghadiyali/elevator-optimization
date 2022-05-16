# elevator-optimization

Scenarios and Requirements:

1. An elevator can move up, down or standstill.

2. An elevator can transfer passengers from one floor in a building to another floor in the minimum time possible.

3. Elevator door can only open when it is standstill on a floor (i.e. not moving).

4. Let’s first discuss the number of floors that a building can have. Let’s just assume that our system has 200 floors.. When we are gathering requirements, we need to make sure that we are still collecting some reasonable requirements.

5. Burj Khalifa has around 57 elevators. We can assume in our system we have around 100 elevators.

6. Then there are some requirements related to each elevator like:
a. Number of passengers / Load on the elevator
b. Moving speed of the elevator

7. Now fourth requirement is about what we would like to minimize.
a. Do we like to minimize the wait time of the passengers?
b. Or do we like to minimize the overall wait time in the system?

8. If we want to have zone wise consideration of elevators, a zone is the set of floors that are covered by a set of elevators, we can divide all floors into zones.

9. In our case of 200 floors and 100 elevators, we can, e.g., divide all the floors into 4 zones:

· From 1–50: operated by 25 elevators

· From 51–100: operated by 25 elevators

· From 101–150: operated by 25 elevators

· From 151–200: operated by 25 elevators

Another way of zoning is to divide all floors into two zones (even and odd floors, etc.).

When we use multiple zones in a building along with a set of elevators assigned to a zone then we can treat each zone independently from each other.

If we use the first approach of 4 zones then our elevator design problem then boils down to 50 floors and 25 elevators. On the other hand, if we use the second approach of 2 zones (i.e. odd/even zones), our elevator design problem boils down to 100 floors and 50 elevators. If we need to decide whether to use zone or not and if yes then which zoning approach to use, it all depends on the waiting time requirements and speed of the elevators.

After collecting all the requirements, it is better to identify different objects and actors in the system. These objects and actors help us to identify the classes and interfaces that we need to implement an elevator system. In an elevator system, you can easily find the following objects.

1. Passenger

2. The elevator controller

3. Elevators

4. Then each elevator can have doors, button panels inside the elevators and then buttons

5. Floors

and more.

After identifying the classes and interfaces and the relation between them, it is also important to discuss different use-cases. The most important use-cases include:

· Calling Elevator Car: So, when a passenger wants to go up or down to a different floor he presses the up or down button to call the elevator. This requires scheduling an elevator car to go to the passenger floor.

· Move/Stop the Elevator

· Open/Close the doors

· Indicating moving direction

· Indicating elevator position: the floor where the elevator has reached. This is important to indicate to the passenger so that the passenger can get off the elevator at his destination floor

· Triggering Emergency Breaks

· Making an Emergency call

Now, considering all these scenarios would be the base to create an algorithm that can work efficiently.


Basic Waiting Time for elevators in multistorey for a user:

Total Upvisits with stops (pressed by users inside elevator) = V
Total Upvists without stops (floors missed) = U
Total called Downvisits with stops (floors users called to stop while lift going down) = W
Total Downvisits without stops (floors missed while travelling down) = Y
Total time per floor with stop = T
Total time per floor without stop = t

Minimum Time consumption in normal elevator for single lift = (V*T + U*t) + (W*T + Y*t)

If there are multiple lifts, we need to calculate the minimum of all and then call that lift for the user.

For minimizing this time, Lifts can be set to go on even/odd order but that too won't benefit much. For better optimization, Lifts can use SCAN or LOOK algorithm or better Block system.

To implement this algorithm, we need better clarification on the need and requirements of what are the scenarios like stated above.

Moin Ghadiyali
