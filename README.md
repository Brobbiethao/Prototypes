# Prototypes
Understanding prototypes and how to pass in class instances.

Following this tutorial: https://www.youtube.com/watch?v=riDVvXZ_Kb4

So prototypes..

The explanation is rather simple on how you can pass data through prototypes to create classes. 
This is preferred over creating constructors and supers() because of the ease of understanding the code due to 
cleanliness.

Breakdown at 3:10

-------------------------------------
The below is a simple prototype. It will allow any class to construct an object.

const food = {
  init: function(type) {
    this.type = type
  }
}
-------------------------------------

const food = {
  init: function(type) {
    this.type = type
  }
}

const waffle = Object.create(food) <-------------------

On line 30, waffle is defined as a class. The class having "food" (which is a prototype with methods) as a parameter
can now access the prototype and its objects.
-------------------------------------

We can see how this works in the below code.

const food = {
  init: function(type) {
    this.type = type
  }
}

const waffle = Object.create(food)
waffle.init("banana") <-----------------

Here the parameter passed, waffle.init() is invoked assigning "banana" to the parameter "type".
If you review the prototype, the init: function has (type) as the parameter passed. This is attached to 
the "this.type = type" where type was passed in as "banana".

this.type = "banana"

-------------------------------------

If you've gotten lost. Let's retrack what happened.

const waffle = object.create(food). What happened? waffle = food. food is a prototype. waffle inherited the prototype.

food was a prototype with 2 object which were methods (init, eat). waffle now has both methods available as objects.

waffle.init("banana") is = to waffle.(this.type) type being the param passed which is "banana".

-------------------------------------

That's it. That's prototype inheritance.
