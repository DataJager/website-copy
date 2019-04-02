This is a great opportunity remind mentees of style conventions and to discuss maps, dictionaries versus arrays.

### Reasonable solutions

```python
def twelve_days(start_verse, end_verse):
    song_list = {
        1: ("first", "and a Partridge in a Pear Tree."),
        2: ("second", "two Turtle Doves, "),
        3: ("third", "three French Hens, "),
        4: ("fourth", "four Calling Birds, "),
        5: ("fifth", "five Gold Rings, "),
        6: ("sixth", "six Geese-a-Laying, "),
        7: ("seventh", "seven Swans-a-Swimming, "),
        8: ("eighth", "eight Maids-a-Milking, "),
        9: ("ninth", "nine Ladies Dancing, "),
        10: ("tenth", "ten Lords-a-Leaping, "),
        11: ("eleventh", "eleven Pipers Piping, "),
        12: ("twelfth", "twelve Drummers Drumming, ")}
    song = []
    for day in range(start_verse, end_verse+1):
        song_line = f"On the {song_list[day][0]} day of Christmas my true love gave to me: "
        if day != 1:
          for i in range(day, 0, -1):
              song_line += song_list[i][1]
              song.append(song_line)
        else:
              song_line += "a Partridge in a Pear Tree."
    return song
```
```python
DAYS = ['first', 'second','third','fourth','fifth','sixth',
        'seventh','eighth','ninth','tenth','eleventh','twelfth']
GIFTS = ['a Partridge in a Pear Tree',
        'two Turtle Doves',
        'three French Hens',
        'four Calling Birds',
        'five Gold Rings',
        'six Geese-a-Laying',
        'seven Swans-a-Swimming',
        'eight Maids-a-Milking',
        'nine Ladies Dancing',
        'ten Lords-a-Leaping',
        'eleven Pipers Piping',
        'twelve Drummers Drumming']
def sing():
    return verses(1, len(DAYS))
def verse(num):
    song = _get_beginning(num) + ''.join([_nth_gift(n) for n in range(num, 1, -1)])
    song += '{}{}.\n'.format('and ' if num > 1 else '', GIFTS[0])
    return song
def verses(first, last):
    return ''.join([verse(n)+'\n' for n in range(first, last+1)])
def _get_beginning(n):
    return 'On the {} day of Christmas my true love gave to me, '.format(DAYS[n-1])
def _nth_gift(n):
    return '{}, '.format(GIFTS[n-1])
```
### Common suggestions
- Suggest using a dictionary instead of a pair of arrays. While two arrays do take less memory, a dictionary is much more expandable
- If the student is using Python 3? Suggest [Literal String Interpolation introduced with Python 3.6](https://www.python.org/dev/peps/pep-0498/).
- If the student is using Python <= 3.5, suggest upgrading to Python 3.7 for additional language features.
- Some people need help with running the tests.
- Check indentation.

### Talking points
- Dictionaries vs Arrays vs Lists
- String interpolation
- Style preferences. This exercise is a good opportunity to talk about style conventions like indentation, parameter parenthesis in method declarations, whether to allow for trailing commas, and removing redundant comments.
Given the place in the curriculum it may be worth not going too deep and to not address points that are controversial or personal preference.

### Mentoring notes
- A friendly standard answer about what the student did well, and a 'alternatively: use a map instead of two arrays' , will be all you need for maybe 90% of the submissions.
