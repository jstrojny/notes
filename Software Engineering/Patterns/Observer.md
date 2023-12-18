The observer pattern can be used to notify a system of some event happening in a _different_ system. This can be most easily achieved through the use of two interfaces: an Observer and a Subject.

## Subject
The subject is the system being observed for events, it is responsible for sending notifications when an event happens. An object that implements the Subject interface must implement a notify function to send the notification to each observer. There are multiple ways to achieve this but the simplest is by having the subject hold a list of observers.

This means the subject is also responsible for providing a way to add and remove observers through a public api.

## Observer
The observer is a system that wants to do something when a notification is sent by another system. They generally implements an onNotify function to react to events. 

Observers should not be dependent on their order within the list. If they are those observers should be refactored to remove whatever coupling causes the dependence. 