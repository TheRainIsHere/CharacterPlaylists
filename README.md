# Character Playlists App
## The Idea
I plan to make a web application that stores character playlists. It's a somewhat niche idea I had a year or so back when making a playlist for one of my DnD characters. I was making notes on each of the songs in a separate document about what parts of the song were relevant, how certain lyrics were interpreted from my character's perspective, and what stage of their life that this song related to. I also included some songs about hypothetical situations my character may have ended up in, even though they ended up not being canon. I wanted to make a web app where users could put some basic facts about their character, and annotate songs similar to the [Genius Lyrics](https://genius.com/Hozier-why-would-you-be-loved-lyrics) site. The idea was also to have users be able to share their characters with others, and to find other (public) characters that have songs in common.
## The Goal
Given the constraints of what the course will cover and the resources I can find, I will have to reduce this idea quite a bit. I attempted to get an idea of how Genius Lyrics does their annotation system, but the obfuscation made it very difficult to gather what was going on. I may be able to still show lyrics when opening song details through the Genius API, but that is more of a stretch goal. What I want this app to accomplish is a local user having the ability to store multiple characters (with options to edit, create, and delete them), and each character to hold multiple songs (with options to remove or add them). The characters must have attributes that uniquely identify them, and a space for a short description (if I can make it work, I would also like to allow the user to include an optional picture). At minimum, the songs must be able to show the title, artist, album, tags, and notes. Users will also be able to search songs within the character, and filter by user-defined tags (e.g. non-canon, fully accurate, partially accurate, certain scenario, past event, etc.).
### "If I can swing it" Goals
- Include lyrics
- Users annotate lyrics
- Import/export playlists using YouTube Music (and Spotify, but that would be stretching further)
- Multiple users (maybe multiple local users, maybe hosting it for class somehow) 
## The Plan
Keep it simple to keep it possible; there will only be one user. Despite that, I will still do my best to structure my logic and queries to accommodate more users should I continue this project after this class. I will work with EF Core for creating the database (as that's what is in the textbook), but admittedly I haven't looked too deep into that yet. I will be using [YouTubeMusicAPI](https://github.com/IcySnex/YouTubeMusicAPI) to grab any song-related data that's needed, so that song objects within a character can be as simple as a YouTube Music ID, tags, and notes. When displaying the list of songs under a character, a wrapper will be used on the songs to return data from the API without needing to store the whole song across multiple characters and users.
## Website Mockups
### Index/Home Page
Below is where the user will find themselves when first launching the app.
<img width="750" height="auto" alt="image" src="https://github.com/user-attachments/assets/5ade5e29-1145-47ea-afc9-5bb136a321c6" /> <br>
The created characters will be listed, along with an image (if provided) and how many songs are in their playlist. When clicking on a character, the user will be brought to the character playlist.
### The Playlist
Here, the songs within a character will be listed.
<img width="750" height="auto" alt="image" src="https://github.com/user-attachments/assets/6f13cc1a-5f29-451e-8262-c33e153402f8" /> <br>
The user will be able to add, remove, and edit songs in this list. When adding or editing a song, the user can apply custom tags to sort and filter the playlist when viewing it from this page. This page also links to the character form.
### Character Form
This will be roughly what the user sees when attempting to create or edit a character.
<img width="750" height="auto" alt="image" src="https://github.com/user-attachments/assets/6aa3711c-8244-4ef3-8297-ff255bdff762" /> <br>
There aren't many required fields, but this allows the user a lot of freedom (especially if the character hasn't been developed thoroughly). <br>
When editing:
- "Editing:" will be the main header
- The form will populate with existing information
- The red button will say "Delete" <br>
When creating a new character:
- "Creating:" will be the main header
- The secondary header will read "New Character"
- The red button will say "Cancel"
