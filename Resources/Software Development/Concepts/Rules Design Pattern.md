# [Rules Design Pattern](https://www.michael-whelan.net/rules-design-pattern/)

The Rules Pattern works by extracting out each rule to a file, separating the rules from the rules processing
logic (applying the Single Responsibility Principle).
This makes it easy to add new rules without changing the rest of the system (applying the Open/Closed Principle).

With the Rules Pattern there is an `Evaluator` class/function that loops through a collection of rules and executes them.
It evaluates the result and decides what action to take.
In the simplest case it just executes all the rules, but it is also possible to add some selection logic to each
rule that allows the Evaluator class to decide whether or not to run the rule (such as the `IsMatch()` method on
the `IRule` interface above(see article)).
