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
  - Initializing a New Object:
    ```ruby
    class GoodDog
      def initialize
        puts "This object was initialized!"
      end
    end
    sparky = GoodDog.new
    ```
    - **initialize** method is triggered every time a new GoodDog is instantiated

  - Instance Variables & Instance Methods
    -  Instance Variables does not "die" after the initialize method is run. It "lives on", to be referenced, until the object instance is destroyed.
    ```ruby
    class GoodDog
      def initialize(name)
        @name = name
      end

      def speak
        puts "#{@name} says arf!"
      end
    end

    sparky = GoodDog.new("Sparky")
    sparky.speaks
    ```
  - Accessor Methods
    - For example, resetting the name 
    ```ruby
    def change_info(n, h, w)
      @name = n
      @height = h
      @weight = w
    end
    ```

    ```ruby
    sparky.set_name = "Spartacus"
    ```

    - the way ruby implements the Equal sign is important


    - And that's how they read the name:
    ```ruby
    def get_name
      @name
    ends
    ```

    - and that's how you should call it
    ```ruby
    puts sparky.get_name
    ```

    - also I think the `puts` can be in the method as well

  - getter and setter for Rubyist
    - **attr_accessor**
    - this automatically create these getter and setter methods for us
    ```ruby
    attr_accessor :name, :height, :weight
    ```
    - put this at the top of the class
    - this includes both `attr_reader` and `attr_writer`

  - Using `self`
    -  It turns out that instead of calling the name=, height= and weight= setter methods, what we did was create three new local variables called name, height and weight. That's definitely not what we wanted to do.

    - To **disambiguate** from creating a local variable, we need to use self.name= to let Ruby know that we're calling a _method_.

    ```ruby
    def change_info(n, h, w)
      self.name = n
      self.height = h
      self.weight = w
    end
    ```

### Class Variables
  - variables for an entire class
  - using two @ symbols like so: **@@**

### Constants
  - define a constant by using an upper case letter;
  - most Rubyists will make the entire variable uppercase.
  - that will never change for any reason
  - It is possible to reassign a new value to constants but Ruby will _throw a warning_.

### The to_s Method
  - By default, the to_s method returns the name of the object's class and an encoding of the object id

  ```ruby
  puts object_name
  # and this is equivalent to the one below
  puts sparky.to_s
  ```
  - puts method automatically calls to_s on its argument if we `puts` an object.
  - `p` doesnt call `to_s`, but call `inspect`

  ```ruby
  # the following are equivalent
  puts sparky.inspect
  p sparky
  ```

### self
  - inside of an instance method, references the instance (object) that called the method - the **calling object**. Therefore, self.weight= is the same as sparky.weight=.
    - this means the object assigned to `sparky = GoodDog.new`

  - outside of an instance method, references the class and can be used to define class methods. Therefore, def self.name=(n) is the same as def GoodDog.name=(n).
    - this means its the class GoodDog itself