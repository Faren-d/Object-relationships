# Object-relationships

## 
![object-relationships1](https://github.com/user-attachments/assets/4338286c-8728-4fb3-9b97-6b32b9180f24)

## Association

Identify the relationship: Determine how the classes are related. Take an example of zookeeper and tool. In this case, it's a "uses" relationship between Zookeeper and Tool.

1. Instantiation:

Instantiation means creating objects from classes. For example, ```bucket = Tool("bucket")``` creates a Tool object named "bucket".

2. Association:

We model the association by allowing zookeepers to pick up, use, and put down tools.

The Tool class hase a ``` user ``` attribute to track which zookeeper is currently using it.

The Zookeeper class has a ``` current_tool ``` attribute to track which Tool they are currently holding.

3. Methods for interaction:

```pick_up_tool()``` Allows a Zookeeper to start using a Tool if it's available.

``` put_down_tool()```: Allows a Zookeeper to stop using their current Tool.

```use_tool()```: Demonstrates how a Zookeeper uses their current Tool.

Example: 

```dash
class Tool:
    def __init__(self, name):
        self.name = name
        self.user = None

    def use(self):
        if self.user:
            print(f"The {self.name} is being used by {self.user.name}.")
        else:
            print(f"The {self.name} is not currently in use.")

class Zookeeper:
    def __init__(self, name):
        self.name = name
        self.tools = []  # A list to store multiple tools

    def pick_up_tool(self, tool):
        if tool.user:
            print(f"Sorry, the {tool.name} is already in use by {tool.user.name}.")
        else:
            self.tools.append(tool)
            tool.user = self
            print(f"{self.name} picked up the {tool.name}.")

    def put_down_all_tools(self):
        for tool in self.tools:
            print(f"{self.name} put down the {tool.name}.")
            tool.user = None
        self.tools = []  # Clear the tools list

    def use_all_tools(self):
        if not self.tools:
            print(f"{self.name} is not holding any tools to use.")
        else:
            for tool in self.tools:
                print(f"{self.name} is using the {tool.name}.")
                tool.use()

# Create instances
bucket = Tool("bucket")
broom = Tool("broom")
rake = Tool("rake")
john = Zookeeper("John")

# Demonstrate usage with for loops
tools = [bucket, broom, rake]

for tool in tools:
    john.pick_up_tool(tool)

john.use_all_tools()
john.put_down_all_tools()

# Check the status of all tools
for tool in tools:
    tool.use()
```

The basic for loop structure:
```dash
for item in collection:
```
    
