**if statement**
syntax: if (condition)
```
x = int(input()"What's x? "))
y = int(input("Waht's y? "))

if x < y:
	print("x is less than y")
```

using def() function

```
def main():
	 x = int(input("What's x? "))
	 if is_even(x):
		 print("Even")
	else:
		print("Odd")

def is_even(n):
	if n % 2 == 0:
		return True
	else:
		return Flase
```

to make the code above more pythonic

```
def is_even(n):
	return True if n % 2 == 0 else False
```

PHP
<?=(condition) ? True : False ?>

to make it more readable

```
def is_even(n):
	return n % 2 == 0
```

**match Statement**

```
# using if statement

name = input("What's your name? ")

if name == "Harry" or name == "Hermione" or name == "Ron":
    print("Gryffindor")
elif name == "Draco":
    print("Slytherin")
else:
    print("Who?")
```

```
match name:
    case "Harry":
        print("Gryffindor")

    case "Hermione":
        print("Gryffindor")

    case "Ron":
        print("Gryffindor")

    case "Draco":
        print("Slytherin")

    case _: // underscore means whatever case has not yet been handled
        print("Who?")
```

more readable way
```
match name:
    case "Harry" | "Hermione" | "Ron":
        print("Gryffindor")

    case "Draco":
        print("Slytherin")

    case _:
        print("Who?")
```

