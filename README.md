## Integration of a Mathematical Calulations with a Chat Completion System using LLM Function-Calling

### AIM:
To design and implement a Python function for calculating the volume of a cylinder, integrate it with a chat completion system utilizing the function-calling feature of a large language model (LLM).

### PROBLEM STATEMENT:
Design and integrate a Python function that calculates the volume of a cylinder, and enable the function to be called through a chat completion system, simulating an LLM interface.
### DESIGN STEPS:

#### STEP 1:Design the Python Function for Volume Calculation
Design the Python Function for Volume Calculation
Where:

(V) is the volume of the cylinder.
(r) is the radius of the base of the cylinder.
(h) is the height of the cylinder.
(\pi) is approximately 3.14159.

#### STEP 2:Create a Chat Completion System
The chat system will:

Take user input as queries.
Detect when the user wants to calculate the volume of a cylinder.
Call the volume calculation function when the user provides the required parameters (radius and height).

#### STEP 3:Integrate the Function with the LLM's Function-Calling Feature
In a system utilizing an LLM with function-calling capabilities:

The function must be defined to be invoked through the LLM interface.
The LLM must be able to extract values for radius and height from the user’s query and pass them to the function

### PROGRAM:
```py
import math
from typing import Dict, Any


def calculate_cylinder_volume(radius: float, height: float) -> float:
    return math.pi * radius * radius * height



function_schema = {
    "name": "calculate_cylinder_volume",
    "description": "Calculate the volume of a cylinder using radius and height.",
    "parameters": {
        "type": "object",
        "properties": {
            "radius": {"type": "number", "description": "Radius of the cylinder"},
            "height": {"type": "number", "description": "Height of the cylinder"}
        },
        "required": ["radius", "height"]
    }
}


def chat_completion_system(user_message: str) -> Dict[str, Any]:
    

    # Asking user for input
    radius = float(input("Enter radius: "))
    height = float(input("Enter height: "))

    # Function calling activated
    volume = calculate_cylinder_volume(radius, height)

    
    response = {
        "function_name": "calculate_cylinder_volume",
        "arguments": {
            "radius": radius,
            "height": height
        },
        "result": volume
    }

    print("\nFunction called:", response["function_name"])
    print("Arguments:", response["arguments"])
    print("Cylinder Volume =", response["result"])

   
    print("Name : Sumith M")
    print("Reg No : 212224230279")

   

    return response


chat_completion_system("Calculate the volume of a cylinder")
```

### OUTPUT:

<img width="582" height="269" alt="image" src="https://github.com/user-attachments/assets/c9607132-32bc-481a-b662-11a96076296f" />



### RESULT:
Thus, the Python program to calculate cylinder volume and integrate it with an LLM chat system using function-calling was successfully designed and executed.
