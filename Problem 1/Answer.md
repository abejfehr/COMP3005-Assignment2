The thought process is vaguely outlined below.

CD
--
- Title
- Artist
- Release Date
- Label
- Producer
- Songs(collection)

**Note:** "Various Artists" is used for CD's that are a compilation

### Thoughts
- Label or producers could be a key, but besides that there's nothing. Titles, artists, release dates, and songs can all share names. This is why I added an ID field

Song
----
- Title
- Author
- Publishing Company
- Lyrics
- Tracks(collection)

### Thoughts
- The lyrics of the song can't be a key. Covers of this song may have the exact same lyrics, so I can't go by that.
- The title, author, and publishing company can't be the key for a song.

Track
-----

Separate for each instrument, like drum tracks, vocal track, etc that all come together to produce one song.

- Instrument
- Name(could be the key)

Database Grammar
----------------
- One CD must contain zero or more songs
- One song may be on one or more CDs
- One song may consist of one or more tracks
- One track must be in one or more songs

Please refer to the accompanying E-R Diagram