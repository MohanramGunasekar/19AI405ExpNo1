<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>VACUUM CLEANER:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>VACUUM CLEANER</strong></td>
    <td><strong>ABSORB DIRT</strong></td>
     <td><strong>Rooms</strong></td>
    <td><strong>CLEANING AGENT</strong></td>
    <td><strong>Location</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

<h3>PROGRAM</h3>
<p>NAME: MOHANRAM GUNASEKAR</p>
<p>REG NO: 212223240095</p>


```python
class VacuumCleanerAgent:

    def __init__(self):
        self.environment = ["Dirty", "Clean", "Dirty"]
        self.location = 0
        self.performance = 0

    def sense(self):
        return self.environment[self.location]

    def clean(self):
        print(f"Room {self.location + 1} is Dirty.")
        print("Cleaning the room...\n")
        self.environment[self.location] = "Clean"
        self.performance += 10

    def move(self):
        print(f"Moving from Room {self.location + 1}...")
        self.location = (self.location + 1) % len(self.environment)
        print(f"Reached Room {self.location + 1}\n")
        self.performance -= 1

    def act(self):
        percept = self.sense()

        print("--------------------------------")
        print(f"Current Room : {self.location + 1}")
        print(f"Room Status  : {percept}")

        if percept == "Dirty":
            self.clean()
        else:
            print("Room is already clean.\n")

        self.move()

    def display_environment(self):
        print("Environment Status")
        for i in range(len(self.environment)):
            print(f"Room {i + 1}: {self.environment[i]}")
        print()

def main():
    agent = VacuumCleanerAgent()

    print("========== VACUUM CLEANER AGENT ==========\n")

    print("Initial Environment")
    agent.display_environment()

    for i in range(len(agent.environment)):
        agent.act()

    print("Final Environment")
    agent.display_environment()

    print("Final Performance Measure:", agent.performance)


if __name__ == "__main__":
    main()

```


## OUTPUT
```text
========== VACUUM CLEANER AGENT ==========

Initial Environment
Environment Status
Room 1: Dirty
Room 2: Clean
Room 3: Dirty

--------------------------------
Current Room : 1
Room Status  : Dirty
Room 1 is Dirty.
Cleaning the room...

Moving from Room 1...
Reached Room 2

--------------------------------
Current Room : 2
Room Status  : Clean
Room is already clean.

Moving from Room 2...
Reached Room 3

--------------------------------
Current Room : 3
Room Status  : Dirty
Room 3 is Dirty.
Cleaning the room...

Moving from Room 3...
Reached Room 1

Final Environment
Environment Status
Room 1: Clean
Room 2: Clean
Room 3: Clean

Final Performance Measure: 17
```




<h3>RESULT</h3>
The Program is excuted successfully.

