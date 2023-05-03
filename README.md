# C-SHARP-Events

events are a way to enable communication between objects. An event is essentially a notification that one object sends to other objects to let them know that a certain action has occurred.

Here is an example of how to declare and use events in C#:

// Declare a delegate for the event handler
public delegate void EventHandler(object sender, EventArgs e);

// Declare an event using the delegate
public event EventHandler MyEvent;

// Raise the event
MyEvent?.Invoke(this, EventArgs.Empty);
In this example, we first declare a delegate for the event handler. This delegate specifies the signature of the method that will handle the event. It takes two parameters: an object that represents the sender of the event, and an EventArgs object that provides any additional information about the event.

We then declare an event using the delegate. This event can be subscribed to by other objects, which will receive notifications when the event is raised.

Finally, we raise the event by invoking the delegate. We use the null-conditional operator (?.) to ensure that the event is only raised if there are subscribers. We pass in the current object as the sender, and an instance of EventArgs.Empty as the event arguments.

To subscribe to an event, you use the += operator to add an event handler method to the event. For example:

makefile

MyEvent += MyEventHandler;
This adds the MyEventHandler method as a handler for the MyEvent event. When the event is raised, the MyEventHandler method will be called, with the sender and event arguments passed in as parameters.

To unsubscribe from an event, you use the -= operator to remove the event handler method. For example:

Copy code
MyEvent -= MyEventHandler;
This removes the MyEventHandler method as a handler for the MyEvent event. It will no longer be called when the event is raised.
