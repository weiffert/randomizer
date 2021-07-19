# Randomizer

Create random Spotify playlists given a set of parameters

## Application Goals

1. Allow users to break out of similar music and discover new parts of Spotify. This is by obfuscation of what is being listened to. Spotify supports radio and playing of similar music. This is the "anti-radio." 
2. Easy interface to allow playlist generation, online playback, and seeding of music type to listen to.

### Deliverables

1. Web interface
2. User sign in
3. Playlist creation
4. Playback integration (save for 2.0)
5. Powerful search features exposing song metadata
6. Randomization of music

## Structure

1. Node.js backend
This will handle authentication, tokens, and contact the Spotify API. All application logic will be done through the backend.
2. React frontend
Display data in a pretty way and support easy user interactions.
3. Stretch: try making an electron app!

### [API](https://developer.spotify.com/documentation/web-api/reference/#endpoint-get-users-saved-tracks)

#### Search API
1. Search Spotify Catalog information about albums, artists, playlists, tracks, shows, or epsides that match a keyword (album, artist, playlist, track, show, episode) string

#### Browse API
1. Get all new releases for a specific country up to a limit
2. Get recommendations given a seed (artist, genre, tracks, acousticness, danceability, duration, energy, instrumentalness, key, liveness, loudness, mode, popularity, speechiness, tempo, time signature, valence)
3. Get recommendations Genres

#### Library API
1. Get User's Saved Albums
2. Get User's Saved Tracks

#### Playback API
1. Start/Resume a User's Playback
2. Pause a User's Playback
3. Skip, seek, ...
4. Get user's recently played tracks
5. Add an item to queue

#### Playlist API
1. Create a playlist (auto empty)
2. Get a playlist
3. Add items to a playlist

#### Tracks API
1. Get Several tracks catalog information based on spotify IDs
2. Get audio features for a track
3. Get audio analysis for a track

#### Profile API
1. Get User's profile

## Code Flow
1. Authentication. Sign in or Refresh Token
2. Home Page
3. Look up song information
4. Generate playlist with seed (may be from song)
5. Generate random playlist from spotify catalog (filter saved songs?)
6. Generate random playlist from saved content
7. Generate what are my friends listening to that I am not playlist
7. View playlist lists
8. View playlist content
7. Sign out

### Views 
1. Unauthenticated
2. Playlist view
3. Playlist generation
4. Song inspection
5. Playlist inspection

### Transitions
1. Unauthenticated -- authentication -> playlist view
2. Playlist view -- view playlist -> playlist inspection
3. Playlist view -- generate playlist -> playlist generation
4. Playlist view -- inspect song -> song inspection
5. Playlist generation -- inspect song -> song inspection
6. Playlist inpsection -- inspect song -> song inspection
7. Playlist view -- sign out -> unauthenticated