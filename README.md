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

The basic for loop structure:
```dash
for item in collection:
```
    
