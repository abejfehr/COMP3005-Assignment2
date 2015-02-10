The database would need to store the positions of the chords within the song, as well as which bar they're in. That must mean that a chord object could be like:

|Chord
|-----
|Value(the actual chord, perhaps a string)
|bar_position
|chord_position

**Thoughts:**
- The chord position would store the index of the chord relative to the song
- The bar position would be the same for a number of chords in a song, since there are more than one chord in a bar

Of course, to be able to store books and users we'll need other additional objects

|Book
|----
|title
|page_offset

**Thoughts:**
- The title of the book can't be the key, since other books could have the same title. I may make a separate ID for this

|User
|----
|username
|password

**Thoughts:**
- The username can be the key

|Song
|----
|title
|chords
|page_num

Search
------
In order to be able to select chords by sequence, you'd have to make a complicated select statement. For example, to select one of the more common sequences: E, B, C#m, A; we'd have to do the following select statement:

    select * from chords where chord="E" and position=(
      select position from chords where chord="B" and position=(
        select position from chords where chord="C#m" and position=(
          select position from chords where chord="A"
          )-1
        )-2
      )-3;

The above SQL should return the first row where the E, B, C#m and A chords appear in sequence.

Please refer to the accompanying E-R Diagram