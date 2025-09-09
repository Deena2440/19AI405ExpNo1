<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: DEENATHAYLAN K</h3>
<h3>Register Number: 212224040058</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
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
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
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

 # PROGRAM:

```python
import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.performance = 0
        self.current_room = 1  # Start in Room 1
        self.rooms = {1: 0.0, 2: 0.0}  # Store patient temperatures

    def sense_environment(self):
        # Randomly assign patient temperatures to rooms
        for room in self.rooms:
            self.rooms[room] = round(random.uniform(97.0, 102.0), 1)

    def prescribe_medicine(self, room):
        temperature = self.rooms[room]
        if temperature > 98.5:
            print(f"Room {room}: Patient has fever ({temperature}°F). Prescribing medicine ✅")
            self.performance += 1
        else:
            print(f"Room {room}: Patient is healthy ({temperature}°F). No medicine needed ❌")

    def move_to_other_room(self):
        # Movement decreases performance
        self.current_room = 2 if self.current_room == 1 else 1
        self.performance -= 1
        print(f"Agent moved to Room {self.current_room} (Performance -1)")

    def run(self, cycles=3):
        print("PEAS Description:")
        print("Performance: Treating unhealthy patients, minimize movement")
        print("Environment: Rooms, Patients")
        print("Actuators: Medicine, Treatment")
        print("Sensors: Location, Temperature\n")

        for i in range(cycles):
            print(f"\n--- Cycle {i+1} ---")
            self.sense_environment()
            self.prescribe_medicine(self.current_room)
            self.move_to_other_room()

        print(f"\nFinal Performance Score: {self.performance}")

agent = MedicinePrescribingAgent()
agent.run(cycles=5)
```

## OUTPUT:

<img width="1608" height="1087" alt="Screenshot 2025-09-09 134833" src="https://github.com/user-attachments/assets/8a36443e-0250-4229-8cf5-5897960e518d" />


## RESULT:
Thus, the experiment was executed successfully and the working of the AI Agent with PEAS description was verified.
