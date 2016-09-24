It’s worth noting that the nil object is special, in that it is the only Ruby object that is false in a boolean context, apart from false itself. We can see this using !! (read “bang bang”), which negates an object twice, thereby coercing it to its boolean value:

```
>> !!nil
=> false
```

In particular, all other Ruby objects are true, even 0:
```
>> !!0
```





### Methods for array
In addition to length (seen in the first line above), arrays respond to a wealth of other methods:

```
>> a
=> [42, 8, 17]
>> a.empty?
=> false
>> a.include?(42)
=> true
>> a.sort
=> [8, 17, 42]
>> a.reverse
=> [17, 8, 42]
>> a.shuffle
=> [17, 42, 8]
>> a
=> [42, 8, 17]
```

### Mutate (bang!)
Note that none of the methods above changes a itself. To mutate the array, use the corresponding “bang” methods (so-called because the exclamation point is usually pronounced “bang” in this context):

```
>> a
=> [42, 8, 17]
>> a.sort!
=> [8, 17, 42]
>> a
=> [8, 17, 42]
```

### Push (<<)
You can also add to arrays with the push method or its equivalent operator, <<:

```
>> a.push(6)                  # Pushing 6 onto an array
=> [42, 8, 17, 6]
>> a << 7                     # Pushing 7 onto an array
=> [42, 8, 17, 6, 7]
>> a << "foo" << "bar"        # Chaining array pushes
=> [42, 8, 17, 6, 7, "foo", "bar"]
```

### Range and `to_a` function ((0..9).to_a)

A range can be converted to an array by applying `.to_a` function. Note the importance of brackets around the range.
```
>> 0..9
=> 0..9
>> 0..9.to_a              # Oops, call to_a on 9.
NoMethodError: undefined method `to_a' for 9:Fixnum
>> (0..9).to_a            # Use parentheses to call to_a on the range.
=> [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
Though 0..9 is a valid range, the second expression above shows that we need to add parentheses to call a method on it.

```
>> ('a'..'e').to_a
=> ["a", "b", "c", "d", "e"]

>> ('a'..'z').to_a.shuffle[0..7].join
=> "nehkiubj" 
```



### Block variable |i|
```
>> (1..5).each { |i| puts 2 * i }
2
4
6
8
10
=> 1..5
```
The range’s each method can handle a block with a single local variable.

Alternatively,
```
>> (1..5).each do |i|
?>   puts 2 * i
>> end
2
4
6
8
10
=> 1..5
```

### Times function
```
>> 3.times { puts "Betelgeuse!" }   # 3.times takes a block with no variables.
"Betelgeuse!"
"Betelgeuse!"
"Betelgeuse!"
=> 3
>> (1..5).map { |i| i**2 }          # The ** notation is for 'power'.
=> [1, 4, 9, 16, 25]
>> %w[a b c]                        # Recall that %w makes string arrays.
=> ["a", "b", "c"]
>> %w[a b c].map { |char| char.upcase }
=> ["A", "B", "C"]
>> %w[A B C].map { |char| char.downcase }
=> ["a", "b", "c"]
```


### Map function
```
>> (1..5).map { |i| i**2 }          # The ** notation is for 'power'.
=> [1, 4, 9, 16, 25]
>> %w[a b c]                        # Recall that %w makes string arrays.
=> ["a", "b", "c"]
>> %w[a b c].map { |char| char.upcase }
=> ["A", "B", "C"]
>> %w[A B C].map { |char| char.downcase }
=> ["a", "b", "c"]
```


### Hashes (Key value pair)
```
>> user = {}                          # {} is an empty hash.
=> {}
>> user["first_name"] = "Christopher"     # Key "first_name", value "Christopher"
=> "Christopher"
>> user["last_name"] = "Zeng"        # Key "last_name", value "Zeng"
=> "Zeng"
>> user["first_name"]                 # Element access is like arrays.
=> "Christopher"
>> user                               # A literal representation of the hash
=> {"last_name"=>"Zeng", "first_name"=>"Christopher"}
```

#### hashrocket (=>)
Instead of defining hashes one item at a time using square brackets, it’s easy to use a literal representation with keys and values separated by =>, called a “hashrocket”:

```
user = { "first_name" => "Michael", "last_name" => "Hartl" }
```
