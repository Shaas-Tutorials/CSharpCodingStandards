(Back)[README.md]

# Design Principles

AKA object oriented stuff.

This document lists various design principles that are not specific to C#.

## Encapsulation

Encapsulation is the idea of putting data and the methods that operate on that data into the same place, such as a class. Furthermore, the internal implementation (the storage of the data) is hidden from external consumers of the class, who work on the data through a public interface. In practice, this typically means providing access to properties through accessors (get;set;) and methods (for actions/work) instead of exposing fields directly. Another example is that a List<T> might be used internally to store something, but is exposed to callers as an ICollection<int> or IEnumerable<int>.

See https://en.wikipedia.org/wiki/Encapsulation_(computer_programming) for more information.

## DRY - Don't Repeat Yourself

Copy/pasting of code is generally bad. If you find yourself copying code from somewhere else and pasting it in, consider putting the code into a common base class (creating a common base class if one doesn't exist), into a static method of a static utility class, or into its own instanced utility class.

But it goes even further to things like build tooling. Code generators, SQL generators, etc. help to put the logic in one place, even if there are then several artifacts.

See https://en.wikipedia.org/wiki/Don%27t_repeat_yourself for more information.

## SRP - Single Responsibility Principle

A type (class, struct, interface) should do one thing, and do it well. An example of a class that breaks this rule: The WebMenu control, which does at least two big tasks: (1) displaying the menu control on the web page, and (2) providing the remoting gateway between Web and App tiers. That should be two separate classes.

See https://en.wikipedia.org/wiki/Single_responsibility_principle for more information.

## Dark patterns

Dark patterns are behaviors or artifacts that include undesirable behavior. I.e., don't do these things.

* (Cargo cult programming)[https://en.wikipedia.org/wiki/Cargo_cult_programming] - Ritual use of code without purpose or properly knowing its purpose.
* (Copy paste programming)[https://en.wikipedia.org/wiki/Copy_and_paste_programming] - Copying code from elsewhere, resulting in higher maintenance effort and larger code base.
