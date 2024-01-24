---
title: Set Operations
Created: 2023-10-22 14:10
tags:
  - SQL
aliases:
---

# Set Operations
- Sets can be combined through a few different operations.
	- **Unions**
	- **Intersection**
	- **Difference**
	- **Symmetric Difference**


## Set Union
- `.union()` will merge two sets.

![[Pasted image 20231022141203 1.png]]

```Python
prepare_to_py = {'rock', 'heavy metal', 'electice guitar', 'synth'}
py_and_dy = frozenset({'classic', 'rock', 'electirc guitar', 'rock and roll'})

combined_tags = prepare_to_py.union(py_and_dy)
print(combined_tags)

'''
Option two to combined sets
'''

frozen_combined_tags = py_and_dy | prepare_to_py
```

```Python
song_data = {'Retro Words': ['pop', 'warm', 'happy', 'electronic'],
'Wait For Limit': ['rap', 'upbeat', 'romance'],
'Stomping Cue': ['country', 'fiddle', 'party'],
'Lowkey Space': ['electronic', 'dance', 'synth']}

user_tag_data = {'Lowkey Space': ['party', 'synth', 'fast', 'upbeat'],
'Retro Words': ['happy', 'electronic', 'fun', 'exciting'],
'Wait For Limit': ['romance', 'chill', 'rap', 'rhythmic'],
'Stomping Cue': ['country', 'swing', 'party', 'instrumental']}

# Write your code below!
new_song_data = dict()

for key,val in song_data.items():
	song_tag_set = set(val)
	user_tag_set = set(user_tag_data[key])
	new_song_data[key] = song_tag_set | user_tag_set

print(new_song_data)
```

## Set Intersection
- `intersection()` returns a new set or frozen set from two or more lists of all the elements that are in common.
- The type of set on the left side of the operand determines the created set.

```Python
prepare_to_py = {'rock', 'heavy metal', 'electice guitar', 'synth'}
py_and_dy = frozenset({'classic', 'rock', 'electirc guitar', 'rock and roll'})

frozen_interesected_tags = py_and_dry.intersection(prepare_to_py)

'''
The alternative method
'''

intersected_tages = prepare_to_py & py_and_dry
```

```Python
song_data = {'Retro Words': ['pop', 'warm', 'happy', 'electronic', 'synth'],
'Wait For Limit': ['rap', 'upbeat', 'romance'],
'Stomping Cue': ['country', 'fiddle', 'party'],
'Lowkey Space': ['electronic', 'dance', 'synth', 'upbeat'],
'Back To Art': ['pop', 'sad', 'emotional', 'relationship'],
'Blinding Era': ['rap', 'intense', 'moving', 'fast'],
'Down To Green Hills': ['country', 'relaxing', 'vocal', 'emotional'],
'Double Lights': ['electronic', 'chill', 'relaxing', 'piano', 'synth']}

user_recent_songs = {'Retro Words': ['pop', 'warm', 'happy', 'electronic', 'synth'],
'Lowkey Space': ['electronic', 'dance', 'synth', 'upbeat']}

# Write your code below!
tags_int = set(user_recent_songs['Retro Words']) & set(user_recent_songs['Lowkey Space'])
#print(tags_int)

recommended_songs = dict()
for key,val in song_data.items():
	for val in song_data[key]:
		if val in tags_int:
			if key not in user_recent_songs:
				recommended_songs[key] = val

print(recommended_songs)
```

## Set Difference
`difference()` find unique items in one set.
```Python
prepare_to_py = {'rock', 'heavy metal', 'electice guitar', 'synth'}
py_and_dy = frozenset({'classic', 'rock', 'electirc guitar', 'rock and roll'})

only_in_prepare_to_py = prepare_to_py.difference(py_and_dry)

'''
Alternative method
'''
only_in_py_and_dry = py_and_dry - prepare_to_py
```

## Symmetric Difference
- `symmetric_difference()` or `^` a resulting set will include elements which are not in the other. Only unique items to each set
- The set can be updated with `symmetric_difference_update()` to update the original set with the result instead of returning a new set or frozen set.
```Python
prepare_to_py = {'rock', 'heavy metal', 'electice guitar', 'synth'}
py_and_dy = frozenset({'classic', 'rock', 'electirc guitar', 'rock and roll'})

exclusive_tags = prepare_to_py.symmetric_difference(py_and_dry)

'''
Alternative method
'''
frozen_exclusive_tags = py_and_dry ^ prepare_to_py
```

```Python
user_song_history = {'Retro Words': ['pop', 'warm', 'happy', 'electronic', 'synth'],
'Stomping Cue': ['country', 'fiddle', 'party'],
'Back To Art': ['pop', 'sad', 'emotional', 'relationship'],
'Double Lights': ['electronic', 'chill', 'relaxing', 'piano', 'synth']}

friend_song_history = {'Lowkey Space': ['electronic', 'dance', 'synth', 'upbeat'],
'Blinding Era': ['rap', 'intense', 'moving', 'fast'],
'Wait For Limit': ['rap', 'upbeat', 'romance', 'relationship'],
'Double Lights': ['electronic', 'chill', 'relaxing', 'piano', 'synth']}

# Write your code below
user_tags = set()
	for key, value in user_song_history.items():
		for val in user_song_history[key]:
			user_tags.add(val)

friend_tags = set()
	for key, value in friend_song_history.items():
		for val in friend_song_history[key]:
			friend_tags.add(val)

unique_tags = user_tags ^ friend_tags

print(unique_tags)
```