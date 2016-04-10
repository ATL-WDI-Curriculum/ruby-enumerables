### Solution


```ruby
people = [
  { name: "Jack",  age: 16 },
  { name: "Sam",   age: 21 },
  { name: "Jill",  age: 23 },
  { name: "Paul",  age: 20 },
  { name: "Mike",  age: 16 },
  { name: "Stan",  age: 70 },
  { name: "Chris", age: 17 },
  { name: "Julie", age: 45 },
  { name: "Suzy",  age: 65 },
  { name: "Eli",   age: 28 },
  { name: "Katie", age: 50 },
  { name: "Ben",   age: 33 }
]

admitted = [ ]

for person in people do 
  if person[:age] > 18
      admitted << person
  end 
  break if admitted.length == 8
end

puts admitted

# Or you could also use && for the loop

for person in people do 
  if person[:age] > 18 && admitted.length < 8
      admitted << person
  end 
end
```



### Bonus solution as a method
```ruby
people = [
  { name: "Jack",  age: 16 },
  { name: "Sam",   age: 21 },
  { name: "Jill",  age: 23 },
  { name: "Paul",  age: 20 },
  { name: "Mike",  age: 16 },
  { name: "Stan",  age: 70 },
  { name: "Chris", age: 17 },
  { name: "Julie", age: 45 },
  { name: "Suzy",  age: 65 },
  { name: "Eli",   age: 28 },
  { name: "Katie", age: 50 },
  { name: "Ben",   age: 33 }
]

def admitted_folks(people, age_limit, club_limit)
	club_folks = []
	
	for person in people do
		if person[:age] > age_limit
			club_folks << person
		end
		
		break if club_folks.length == club_limit
	end
	
	return club_folks
end

puts admitted_folks(people, 21, 3)
```
