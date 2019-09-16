## Quiz: Mass Assignment

???

# Mass Assignment

?: What is a way of passing arguments into a method that pairs a key that functions as the argument name, with its value?

( ) Arguments ( ) Mass Assignment ( ) Keyword Parameters (X) Keyword Arguments

?:

```ruby
def greeting(name, programming_language)
  puts "Hello, #{name}"
  puts "Welcome to the #{programming_language} curriculum"
end

greeting("Ruby", "Leroy Jenkins")
```

What will the code sample above output?

( )
```bash
Hello, Leroy Jenkins
Welcome to the Ruby curriculum
```
(X)
```bash
Hello, Ruby
Welcome to the Leroy Jenkins curriculum
```
( )
```bash
Hello, Ruby
  TypeError: no implicit conversion of Fixnum into String
```
( )
```bash
Hello, Leroy Jenkins
  TypeError: no implicit conversion of Fixnum into String
```

?:

```ruby
def greeting(name, programming_language)
  puts "Hello, #{name}"
  puts "Welcome to the #{programming_language} curriculum"
end

greeting(programming_language: "Ruby", name: "Leroy Jenkins")
```

What will the code sample above output?

( )
```bash
Hello, Leroy Jenkins
Welcome to the Ruby curriculum
```
( )
```bash
Hello, Ruby
Welcome to the Leroy Jenkins curriculum
```
(X)
```bash
ArgumentError: wrong number of arguments (given 1, expected 2)
```
( ) None of the Above

?:

```ruby
def greeting(name:, programming_language:)
  puts "Hello, #{name}"
  puts "Welcome to the #{programming_language} curriculum"
end

greeting(name: "Leroy Jenkins", programming_language: "Ruby")
```

What will the code sample above output?

(X)
```bash
Hello, Leroy Jenkins
Welcome to the Ruby curriculum
```
( )
```bash
Hello, Ruby
Welcome to the Leroy Jenkins curriculum
```
( )
```bash
ArgumentError: wrong number of arguments (given 1, expected 2)
```
( ) None of the Above


?: Which `rat_counter` method below correctly implements the following?

The method should use keyword arguments to take in a hash as an argument: the keys of the hash are `rat_count` and `train_line`. If called with an argument of `rat_count: 2, train_line: "B train"`, the method should return: `There are 2 rats on the B train.`


(x)
``` ruby
def rat_counter(rat_count:, train_line:)
  "There are #{rat_count} rats on the #{train_line}."
end
```
( )
``` ruby
def rat_counter(rat_count, train_line)
  "There are #{rat_count} rats on the #{train_line}."
end
```
( )
``` ruby
def rat_counter(rat_count:, train:)
  "There are #{rat_count} rats on the #{train_line}."
end
```

?: Define a class, `School`, that initializes with a name and a location. The class should also have `attr_accessor`s for `name` and `location`. The `initialize` method should use keyword arguments for those attributes.

Which snippet below is the correct implementation of `School` according to the above spec?


( )
``` ruby
class School
  attr_accessor :name, :location

  def initialize(*args)
    @name = args[0]
    @location = args[1]
  end
end
```
(x)
``` ruby
class School
  attr_accessor :name, :location

  def initialize(name:, location:)
    @name = name
    @location = location
  end
end
```
( )
``` ruby
class School
  attr_accessor :name, :location

  def initialize(name, location)
    @name = name
    @location = location
  end
end
```

?:

```ruby
class User
  attr_accessor :name, :age, :location, :user_name

  def initialize(user_name:, name:, age:, location:)
    @user_name = user_name
    @name = name
    @location = location
    @age = age
  end
end
```

The above code snippet is considered _metaprogramming_.

( ) True (X) False

?:

```ruby
class User
  attr_accessor :name, :gender, :location

  def initialize(attributes)
    attributes.each {|key, value| self.send(("#{key}="), value)}
  end
end
```

How can mass assignment and metaprogramming be used with the code snippet above?

( )
```ruby
User.new(name: "Leroy Jenkins", gender: "other", location: "The Ether")
```
( )
```ruby
User.new("Leroy Jenkins", "other", "The Ether")
```
( )
```ruby
User.new(name: "Leroy Jenkins", location: "The Ether")
```
(X) Both A and C

?: With mass assignment and metaprogramming, we can easily alter the number of attributes in a class and change the hash that we initialize the class with, without editing our initialize method. 

(X) True ( ) False

?: If the data we want from our initialize method changes, what would have to change?

( ) the `initialize` method ( ) the keyword attributes ( ) the keys and values (X) `attr_accessor`

???
