The thought process is vaguely outlined below.

In order to make a "contact"  which will have a ringtone assigned to it, it needs to have 3 things:

|Contact
|-------
|Line
|Susbcriber
|Ringtone

|Susbcriber
|----------
|Name

**Note:** This would be a weak identity, since a subscriber needs a line in order to exist. Name could be a partial key

Ringtone
--------
- Title

Database Grammar
----------------
- One subscriber must have one line
- One line must have one subscriber
- One subscriber may have many lines as contacts
- A line may exist for one susbcriber as a contact
- A line may have one ringtone for a contact
- A ringtone may have one line in a contact

Please refer to the accompanying E-R Diagram
