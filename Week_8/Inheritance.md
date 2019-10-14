# Inheritance in Ruby

  - use **<** symbol to signify that what class is inheriting from the another class

  ### Overriding

    ```ruby
    class Animal
      def speak
        "Hello!"
      end
    end

    class GoodDog < Animal
      attr_accessor :name

      def initialize(n)
        self.name = n
      end

      def speak
        "#{self.name} says arf!"
      end
    end
    ```

    - also we can use **super** if we just adding some stuffs from the original text

    ```ruby
    class GoodDog < Animal
      def speak
        super + " from GoodDog class"
      end
    end
    ```

    - or even use **super** in the **initialize**
    ```ruby
    class GoodDog < Animal
      def initialize(color)
        super
        @color = color
      end
    end
    ```
  
  - Private
    - only can be accessed by other methods in the class
    -  In summary, private methods are not accessible outside of the class definition at all, and are only accessible from inside the class when called without self

  - Protect
    - can be used with `self` 


# Modules

```ruby
# use include to make mixin
include Swimmable
```

  - Namespacing
    - namespacing means organizing similar classes under a module
    - use modules to group related classes

  - container
    - This involves using modules to house other methods
    - very useful for methods that seem out of place within your code

# Difference 
- You can only subclass from one class. But you can mix in as many modules as you'd like.
- If it's an "is-a" relationship, choose class inheritance. If it's a "has-a" relationship, choose modules. Example: a dog "is an" animal; a dog "has an" ability to swim.
- You cannot instantiate modules (i.e., no object can be created from a module). Modules are used only for namespacing and grouping common methods together.