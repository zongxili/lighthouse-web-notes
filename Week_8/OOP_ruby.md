# Object-Oriented Programming in Ruby

- Ruby file names should be in snake_case
- Class / Modules first characters in their names need to be capitalized

- instantiation

  ```ruby
  # good_dog.rb
  class GoodDog
  end
  sparky = GoodDog.new
  ```

  - we've instantiated an object called sparky from the class GoodDog.

### Module
  - Modules are similar to classes in that they contain shared behavior.
  - another way to achieve **polymorphism** in Ruby.
  - A module is a collection of behaviors that is usable in other classes via **mixins**.
  - _However, you cannot create an object with a module._ A module must be mixed in with a class using the include method invocation. This is called a **mixin**. After mixing in a module, the behaviors declared in that module are available to the class and its objects.

  ```ruby
  module Speak
    def speak(sound)
      puts sound
    end
  end

  class GoodDog
    include Speak
  end

  class HumanBeing
    include Speak
  end

  sparky = GoodDog.new
  sparky.speak("Arf!")        # => Arf!
  bob = HumanBeing.new
  bob.speak("Hello!")         # => Hello!
  ```
  This is an example of mixins

### Method Loopup
  - for all classes, use **className.ancestors**
  - working with both mixins and class inheritance
  - only for defined class! Not for declared class with _new_ key word

### States and Behaviors
