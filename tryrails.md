
```
to_s converts values to strings.
to_i converts values to integers (numbers.)
to_a converts values to arrays.
```

##Sort Array 
```
ticket = [12, 47, 35]
ticket.sort
ticket

ticket.sort!
ticket

```

You might notice that the method has an exclamation point at its end. This just signals that we intend for Ruby to directly modify the same array that we've built, rather than make a brand new copy that is sorted. You'll notice that if you try calling ticket again, it will be sorted permanently!

from (tryRuby )[http://tryruby.org/levels/3/challenges/3]
```
> print poem
	=> "My toast has flown from my hand
	And my toast has gone to the moon.
	But when I saw it on television,
	Planting our flag on Halley's comet,
	More still did I want to eat it."

> poem['toast'] = 'honeydew'

> print poem
	=> "My honeydew has flown from my hand
	And my toast has gone to the moon.
	But when I saw it on television,
	Planting our flag on Halley's comet,
	More still did I want to eat it."

```
See how you only changed the first toast? The joke's on you, bread hater.

## Chaining

> poem.lines.to_a.reverse.join

Chaining methods lets you get a lot more done in a single command. Break up a poem, reverse it, reassemble it

### include string function:
> poem.include? "my hand"
	=> true

## Hash/Dictionary (just like python)

```
> books = {}
> books["Gravity's Rainbow"] = :splendid
> books.length
> books["Gravity's Rainbow"] 
```

### building a simple hash

build an empty hash
```
> ratings = Hash.new(0)
```