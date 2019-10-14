# Ruby

- able to change the data type
  - but can't do "string + integer"
- can get ride of patheseias
- assign a const: make a variable starting CAPITAL




The use of #{3+2} in the code above is how you insert Ruby computations into text strings. You can put anything that is Ruby code between the { (left-bracket) and } (right-bracket) characters and Ruby will run it and put the result there instead of those characters. It may not make a lot of sense right now, but you will use this more and more in the book and begin to understand it as you work.




- Get the prompted input from command line
  - use ```variable = gets.chomp```


- Data types Transition
  - String to Number
    ```
    another = gets.chomp
    number = another.to_i
    ```
  - to float points
    ```
    to_f
    ```

- taking command argument
```
first, second, third = ARGV

puts "Your first variable is: #{first}"
puts "Your second variable is: #{second}"
puts "Your third variable is: #{third}"
```


