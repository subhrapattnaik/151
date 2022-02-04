# 151

we created a 3D model using Tinkercad and exported it to A-Frame.


 Now you have an idea of how 3D models are created and used for virtual scenes. We will be learning more about how to create a virtual simulation.
 
 
 Virtual simulation is basically re-creating real-world environments on computer screens
 
 
 for example, you can create a simulation for games or dance clubs, shopping mall simulations and so on.
The beauty of creating virtual simulation is that you can virtually experience things as if they were in the real world without actually visiting there.

We will soon be learning how to create a virtual flight simulation.

-------------------------
entity-component-system is.
In simple terms, 
Entity can be considered an empty container in which multiple components can be attached. 
Entities can be referred to using id.

Components can be understood as the main building blocks in ECS, which contains data and where all logic is implemented by mixing, matching and configuring components.
Once the component is defined, it can be re-used with different entities.



System globally manages the components and entities.
----------------------------------
the entity is represented as <a-entity></a-entity>

attributes of <a-entity> are:
position, rotation, animation, and light
  
 the value in the position attribute represents component data
---------------------------------
  multiple components can be attached to an entity like multiple pieces of puzzles are combined together.

All components together can define how the entity will look and how the entity will behave.
  
-------------------------------
Single-property component:
A single property component consists of the data with single values.
For example, the position is the name of the component and the “-10 3 5” is the data of the component.


Multi-property component:
A multi-property component consists of data with multiple properties and their values
For example, in the light component, data of the component is type, intensity, color, etc.


these data are called properties of the components, and their values are set as -
“type: spot, intensity:1 , color: yellow”

-----------------------------------
  
  
  how a system is represented in A-Frame?
<a-scene> represents the system in A-Frame which globally manages all entities and its components.
  
  --------------------
   custom components in A-Frame
  
  
  We can begin with writing a very basic log component which will display a message in the console log once it is attached to the entity.
  
  we will need a JavaScript file.
 add the JavaScript file ‘Log.js’, and includes that in index.html.
  
  
  To use the registered component, it must be used before <a-scene> in the index.html file
  

To write custom components, we use:
AFRAME.registerComponent (name, definition)
name: is the component name; it is of string data type. Here ‘box’ is the name of the component.
definition: contains the component definition. It is a JavaScript object
 
 which has schema and lifecycle handler methods(init, update, tick, remove, etc).
 
 schema: is an object that defines the property names, their types, and default values. The schema defines the shape of the data.
 
 Lifecycle Handler Methods:
init: This is used to set up the initial state. It is called once when the component is initialized.
update: This is used to modify the entity.
remove: This is used to undo all previous modifications to the entity.
tick: This is used for checking continuous changes. It is called on every render loop of the scene.
 ------------------------
 For our log component, 
 
 let’s define a message data property type via the schema. 
 The ‘message’ property type will have a ‘string’ type and have a ‘default’ value of Hello, World!
 
 Now, this component will log a simple message once when the component’s entity is attached using the .init() handler.
 ------------------------
 The component’s property values defined in the schema can be accessed through this.data.
this points to the entity at which the component is attached.
 
 -----------------------
 
 use in <a-entity log="message:"Hi..its me"></a-entity>
  
  ------------------------------------
  --------------------------------------------------------------------
  will create a simple component that can handle a box's movement from one position to another in the x-direction.
    add it in index .html in <script></script>
  ------------------------
  
  write BOX.js (to register the component)
  move-box is the component name (a string given while registering)
  
  We should update the value of the position attribute of <an-entity> where <a-box> is present.
To do this, we use:
this.el.getAttribute(): to get the current values of the position attribute.
this.el.setAttribute(): to set the updated value of the position attribute.
this.elgives reference to the entity as an HTML element.
  --------------------------------------------
  we should attach this component to the entity to move the box.
 
 
 
 
 
 
