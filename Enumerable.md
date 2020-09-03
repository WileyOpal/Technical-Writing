# Enumerable

The audience for this documentation is Ruby programmers to learn how to use the Enumerable method, which is one of Ruby's most powerful but most misunderstood features.

## What
`Enumerable` is a Ruby module/mixin that specializes `#each` into more useful methods for iterating through your collections. `Enumerable` provides dozens of built-in tools for sorting, searching, and counting whatever `#each` passes to it. Any class that implements `#each` can use these tools.

`Enumerable` output is often in array or hash form.

## How
To use this method, insert `include Enumerable` in your classes that define `#each`. A class that uses `Enumerable` takes the following format:
```ruby
class NameOfClass
   def each
   [...]
   end
   include Enumerable
end
```
Once you define `#each` and `include Enumerable` in a collection, all `Enumerable` methods become available. 

Structures defined in the standard Ruby library like classes, hashes, and arrays don't require you to specify `#each` when using `Enumerable`. Classes and structures that inherit from structures defined in the standard Ruby library also do not require you to specify `#each` when using `Enumerable`.  Pre-written, standard structures in Ruby have `#each` defined internally, which means  `Enumerable` methods have already been built into standard structures. 

### Some Useful `Enumerable` Methods

`Enumerable` is fundamentally about comparisons. Some of these comparisons are inherent to a method, like `#tally` (see below), which always counts the number of instances of items in an array. Other methods, like `#min` (see below) compare items inside a collection and require the programmer to define the basis of that comparison. The following are examples of some interesting and useful `Enumerable` methods.

#### Drop
`Enumerable` can save you a lot of work. For example, the following use of `#drop`  is an `Enumerable` method which removes the first n elements of an array and returns the rest: 
```ruby
lemon = [1, 3, 5, 7, 9, 11]
lemon.drop(2)		
#-> [5, 7, 9, 11]
```
Without using the `Enumerable` method, the same operation takes ten lines of code:
```ruby
result = []
lemon = [1, 3, 5, 7, 9, 11]
x = 0
lemon.each do |item|
  x += 1
  if x > 2
    result << item
  end
end
result
#=> [5, 7, 9, 11]
```

#### Tally
`#tally` counts the number of instances of each element in an array and returns a hash, where each element is a key and the number of times that element appears is the corresponding value:
```ruby
["apple", "pear", "orange", "apple", "kiwi", "kiwi", "kiwi"].tally
#-> {"apple" => 2, "pear" => 1, "orange" => 1, "kiwi" => 3}
```

#### Comparison Methods
When an operation requires a comparison (as in `#min`, `#max`, or `#sort`), you typically specify the comparison operation  so `Enumerable` knows what you want to compare within your collection. For example, `#min` returns the object with the smallest value, but "the smallest value" can be determined on the basis of many parameters. Therefore, the programmer must define the basis of that comparison. The following code specifies a comparison operator to select the string with the shortest length:
```ruby
fruit = ["grapefruit", "plum", "pineapple"]
fruit.min {|a, b| a.length <=> b.length}
#-> "plum"
```

Another Ruby module, [`Comparable`](https://ruby-doc.org/core-2.7.0/Comparable.html), is a set of pre-defined comparisons you can use with `Enumerable` 's comparison methods, but you may also define your own. 


Thanks for reading. See the [Enumerable code here](https://github.com/rubinius/rubinius/blob/master/core/enumerable.rb) and [
the full write-up with code blocks here](https://ruby-doc.org/core-2.7.0/Enumerable.html).
