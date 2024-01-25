# Unnamed patterns and variables

## Context

This new addition allows us to reduce boilerplate code when side effects are our only concern.

Unnamed patterns are an improvement over Record Patterns In Java 19 and Pattern Matching for Switch. 
We should also be familiar with the Record functionality introduced as a preview in Java 14.

Unnamed variables are used when we care only about an operation’s side effects. 
They can be defined as many times as needed, but they cannot be referenced from a later point.

For starters, let’s say we have a simple Car record:
```
public record Car(String name) {}
```
We then need to iterate through a collection of cars to count all cars and do some other business logic:
```
for (var car : cars) {
    total++;
    if (total > limit) {
        // side effect
    }
}
```

While we need to go through every element in the car collection, we don’t need to use it. Naming the variable 
makes the code harder to read, so let’s try the new feature:

```
for (var _ : cars) {
    total++;
    if (total > limit) {
        // side effect
    }
}
```
This makes it clear to the maintainer that the car isn’t used. Of course, this can also be used with a basic for loop:
```
for (int i = 0, _ = sendOneTimeNotification(); i < cars.size(); i++) {
// Notify car
}
```