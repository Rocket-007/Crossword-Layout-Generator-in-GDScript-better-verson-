# Crossword-Layout-Generator-in-GDScript-better-verson-

### I have a [video on this project](https://m.youtube.com/watch?v=zEfwmYxQMeI), be sure to check it out

## This is port on [bryanhelmig's](https://github.com/jeremy886/crossword_helmig) program written in python. 

Given a list of words, this program arranges them into a crossword grid  
and also provides useful methods (yes uses classes) to retrieve and manipulate the data.


### input 
![Example Output](https://github.com/Rocket-007/Crossword-Layout-Generator-in-GDScript-better-verson-/blob/main/screenshots/Screenshot%202022-10-25%209.33.38%20PM.png)
### output
![Example Output](https://github.com/Rocket-007/Crossword-Layout-Generator-in-GDScript-better-verson-/blob/main/screenshots/Screenshot%202022-10-25%209.33.05%20PM.png)



### One can visualize the output as follows:

NOTE  (it is different from the grid output cause at the moment  
it is set to generate a random layout for the same input on each start up)

![Example Output](https://github.com/Rocket-007/Crossword-Layout-Generator-in-GDScript-better-verson-/blob/main/screenshots/Screenshot%202022-10-25%209.35.11%20PM.png)

## Getting Started

**Step 1:** 
```
var word_list = [
	["tamed"],
	["mead"],
	["eat"],
	["ate"],
	["made"],
	["dam"],
	["mated"]]

func _ready():
# if you dont want to put a clue this will solve it
	for v in word_list:
		if v.size() < 2:
			v.append("clue")

#	var start_full = float(OS.get_unix_time())
  
	var layout = Crossword.new(13, 13, '-', 5000, word_list)
	layout.compute_crossword(1) #or maybe(0 or 2) for some reason
	print (layout.word_bank())
	print (layout.solution())
#       print (layout.word_find())
	layout.display()
#	print (layout.display())
	print (layout.legend())
#	print (len(layout.current_word_list), 'out of', len(word_list))
	print (layout.debug)
	
#	var end_full = float(OS.get_unix_time())
#	print ("time: ", end_full - start_full)
...
```
**Step 2:** 
```
# to prevent the randomized grid
# comment out the following code





#line 192
new_coord_list.shuffle() #cause why not?

#line 209
randomize() #dont remove vertical() % (2-0) + 0

# PS. I wasn't really 100% sure where the randomizing was coming from but
# i commented those lines and it worked :3
```
