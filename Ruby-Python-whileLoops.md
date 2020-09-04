# while Loops in Ruby and Python

The target audience for this documentation is programmers who know Ruby and would now like to learn Python. Although **while** loops exist in Ruby, programmers rarely use them. Python programmers, in contrast, do use **while** loops. 

## while Loops Generally

A **while** loop causes a block of code to iterate as long as a quit condition remains `True`. A well-written **while** loop contains at least one quit condition that eventually becomes `False`.

## Ruby Refresher

Here's an example of a **while** loop in Ruby as a refresher:

```ruby
counter = 0

while counter < 4
    puts "The counter is currently #{counter}"
    counter = counter + 1
end
```

The output of this code is:

```ruby
The counter is currently 0
The counter is currently 1
The counter is currently 2
The counter is currently 3
```
This is the quit condition for that loop:

    `counter < 4 `

Ruby **while** loops stop iterating when the quit condition becomes False.  

## Writing A while Loop In Python 

A traditional **while** loop in Python looks almost identical to a **while** loop in Ruby. The following example is a Python version of the Ruby **while** loop shown in the previous section:
```python
counter = 0

while counter < 4:
    print(“The counter is currently %d” % (counter))
    counter += 1
```
The output of this code is:
```python
The counter is 0
The counter is 1
The counter is 2
The counter is 3
```
This **while** loop, like the **while** loop in the preceding Ruby example, also contains a quit condition (`counter < 4`).

The loop iterates when the quit condition evaluates to `True`. The loop stops iterating when the quit condition evaluates to `False`.  

## Practical Uses in Python

Python **while** loops are powerful tools because quit conditions are remarkably flexible. For example, a quit condition could simply be a list or a dictionary. 

In other words, instead of specifying a traditional `True/False` condition, the "condition" can be the name of a list or a dictionary variable. In Python, a list evaluates to `True` if it is not empty; a list evaluates to `False` if it is empty. That is, the loop continues iterating as long as the list is not empty. As soon as the list becomes empty, the loop stops iterating. 

The following example uses a **while** loop to populate two lists:
```python
potential_allergens = ['cats', 'dogs', 'mold', 'dust', 'marigolds']
confirmed_allergens = []
nonallergens = []

# while loop will iterate five times: once for each item in the list
while potential_allergens:
    current_allergen = potential_allergens.pop()
    if current_allergen.endswith('s'):
        confirmed_allergens.append(current_allergen)
    else: 
        nonallergens.append(current_allergen)

#Finally, we print out the final list of confirmed allergens.
print()
print("The confirmed allergens are:")
print(confirmed_allergens)
print()
print("The nonallergens are:")
print(non_allergens)
```
The output of this code is:
```python
The confirmed allergens are:
['marigolds', 'dogs', 'cats']

The nonallergens are:
['dust', 'mold']
```

The preceding **while** loop iterates through the `potential_allergens` list. When the `potential_allergens` list contains at least one item, the quit condition is `True`. When the `potential_allergens` list is empty, the quit condition becomes `False`. The `potential_allergens` list starts with five elements, so the starting condition evaluates to `True`. On every iteration of the loop, the `pop()` function removes one element from the `potential_allergens` list and adds that element to either the list of `confirmed_allergens` or the list of `nonallergens`. After popping the last item off, the `potential_allergens` list becomes empty, so the quit condition becomes `False`.

You can also use **while** loops to process data. The following example relies on a **while** loop to remove every instance of a particular item (`car`) from a list:
```python
vehicles = ['bicycle', 'car', 'boat', 'tricycle', 'unicycle', 'car', 'train', 'boat', 'car']
print(“Starting list: %s” % (vehicles))

#The condition evaluates to True when 'car' is an element in the list 
while 'car' in vehicles:
    vehicles.remove('car')   #Remove 'car' from vehicles

print()
print(“Ending list: %s” % (vehicles))
```
The output of this code is:
```python
Starting list: ['bicycle', 'car', 'boat', 'tricycle', 'unicycle', 'car', 'train', 'boat', 'car']

Ending list: ['bicycle', 'boat', 'tricycle', 'unicycle', 'train', 'boat']
```

The preceding code tells Python to use the remove function to delete each item named `car` from the `vehicles` list. Without the **while** loop, Python would only remove the first `car` item from the list. The **while** loop iterates three times--one time for each instance of `car` in the list. When the list is devoid of `car` items, the loop stops iterating.  

## Practical Uses in Ruby

Unless you want a loop that iterates forever, do not use **while** loops in Ruby. In Ruby, **while** loops are generally used when a loop must be kept running but the programmer does not know the quit condition. For example, a **while** loop keeps a loop active while waiting for data to become available. 

## Avoiding Infinite Loops in Python


It's easy to accidentally omit one word or line of code and find yourself in a **while** loop that runs forever. If you do find yourself in an infinite loop, `Ctrl-C` usually stops the loop. 

To avoid an infinite loop in Python, make sure the code for your **while** loop fulfills both of the following:

* Contains a quit condition.
* Can reach that quit condition. A quit condition only helps you avoid infinite loops if your code eventually reaches the quit condition. 

The example in the [Writing A while Loop In Python](#writing-a-while-loop-in-python) section would iterate infinitely if you didn't increment the counter. Similarly, the Python example from the [Practical Uses in Python](#practical-uses-in-python) section above would also iterate forever if you removed any potential quit conditions. For example, the following code creates an infinite loop:
```python
potential_allergens = ['cats', 'dogs', 'mold', 'dust', 'marigolds']
confirmed_allergens = []
nonallergens = []

# while loop will iterate indefinitely
while potential_allergens:    
    current_allergen = potential_allergens[0]
    # Removed the call to pop().

    # The following if/else block will perpetually process "cats" and
    # never get to "dogs".
    if current_allergen.endswith('s'):
        confirmed_allergens.append(current_allergen)
    else: 
        nonallergens.append(current_allergen)
```
Without the call to `pop()`, the loop never modifies the original list. The `potential_allergens` list continues to evaluate to `True`, so the loop never stops.

## Conclusion

For a more detailed examination of **while** loops, I suggest learning about **break** statements, **continue** statements, and about how **while** loops can interact with user input.

Thanks for reading. May your loops all end exactly when you want them to. For more info, check out the following additional sources: 
* https://en.wikipedia.org/wiki/While_loop 
* [Python Crash Course](https://www.programmer-books.com/wp-content/uploads/2018/06/Python%20Crash%20Course%20-%20A%20Hands-On,%20Project-Based%20Introduction%20to%20Programming.pdf)
* [Learn Ruby the Hard Way](https://learncodethehardway.org/ruby/)
