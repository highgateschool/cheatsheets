# Pseudocode vs Python cheatsheet

## General comments

- The idea of having "standard" pseudocode is an oxymoron, so I'm giving you what the textbook seems to prefer
- There are other attempts at standards. For instance [this LaTeX package](http://mirror.ox.ac.uk/sites/ctan.org/macros/latex/contrib/algorithmicx/algorithmicx.pdf).


## Variables

```pseudocode
JOES_VARIABLE <- 35
```
- Declare constants at start
- Note we use '<-' rather than '='
- Standard style seems to be to use capitals and '\_' not CamelCase

Python:

```python
joes_variable = 35
```

- Use '=' for assignment and '==' for comparison
- Python style is to use lower case for Variables
- Objects get an upper case first letter in the manner of a proper noun
- CamelCase is a Java thing

## Output

```pseudocode
OUTPUT "Something to display on screen"
```

- Use double quotes
- "PRINT" is a BASIC command, so is probably acceptable too

Python:

```python
print( 'Something to display on screen' )
```
- Python style is to use 'single quotes' but "double quotes work fine too"
- Old-style Python didn't treat print as a function so brackets weren't necessary
- You can format output nicely using "{0.%5f}" style notation. Take a look at [this](https://docs.python.org/3/tutorial/inputoutput.html).

## Input

```pseudocode
// First a prompt //

OUTPUT "Say Something"

// Then the actual input //

INPUT CHARLIES_VARIABLE
```

- Probably best separate the prompt (which is output) from the input itself
- There isn't a standard way to write a comment in pseudocode

Python:

```python
charlies_variable = input( 'Say something: ' )
```

- Note that the ```input``` function takes a **prompt as input**.
- It returns a **string as output**.

## Loops

```FOR ... NEXT```

```pseudocode
FOR INDEX = 1 TO 20
	OUTPUT INDEX
NEXT INDEX
```

- You can have a ```STEP``` clause at the end of the ```FOR ... TO``` line to have jumps of 5 at a time or whatever.
- This is a standard "BASIC" loop.

Python:

```python
for i in range( 1 , 21 ):
	print( i )
```

- No NEXT because of indentation.
- ```range( 1 , 20 , 5 )``` will give you jumps of size 5.

```WHILE ... END WHILE```

```pseudocode
i <- 1
WHILE i < 21
	OUTPUT i
	i <- i + 1
END WHILE
```

Python:

```python
i = 1
while i < 20 :
	print ( i )
	i = i + 1
```

- Indentation tells us the end of the loop so no ```ENDWHILE```.
- You can leave the loop at any time using a ```BREAK```. See below...

```REPEAT ... UNTIL```

```pseudocode
i <- 1
REPEAT
	OUTPUT i
	i <- i + 1
UNTIL i = 20
```

Python:
- Doesn't exist.
- Use ```while``` instead and consider using a ```break``` if it helps with structure:

```Python
i = 1
## Standard trick for an infinite loop in Python:
while True:
	print( i )
	i = i + 1
	if i == 20:
		## Next line will leave the loop
		break
```

- Using too many ```break```s can be messy so use sparingly.

## Decision/branching

```pseudocode
INPUT SOMETHING

IF SOMETHING = 20 THEN OUTPUT "You typed 20"
```

- Since "<-" is used for assignment, "=" is not ambiguous in pseudocode.
- If the ```THEN``` block is long then use multiple lines and finish with an ```END IF```.
- ```ELSE``` blocks can be added as required (and finish with an ```END IF```).

Python:

```python
something = input()

if something == 20:
	print( 'You typed 20' )
```

- No ```THEN``` because of the colon.
- No ```END IF``` because of indentation.
- Additional ```elif ...:``` and ```else:``` clauses can be added.


## Arrays/lists

...tbc...
