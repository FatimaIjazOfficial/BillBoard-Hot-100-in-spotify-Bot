# Billboard Hot 100 to Spotify Playlist Project

## Description

This project allows you to create a Spotify playlist of the Billboard Hot 100 songs from a specific date. It scrapes the Billboard website for the top 100 songs and adds them to a newly created private playlist on your Spotify account.

## Prerequisites

Make sure you have the following libraries installed:

- `requests`
- `beautifulsoup4`
- `spotipy`

You can install them using pip:

```sh
pip install requests beautifulsoup4 spotipy
```

## Usage

1. **Scrape Billboard Hot 100:**
   - The script prompts you to enter a date in the format `YYYY-MM-DD`.
   - It then fetches the Billboard Hot 100 songs for that date by scraping the Billboard website.

2. **Spotify Authentication:**
   - The script uses Spotipy to authenticate your Spotify account. You need to provide your Spotify API credentials (`client_id`, `client_secret`, and `redirect_uri`).
   - The script will prompt you to log in to your Spotify account and authorize the application.

3. **Search Spotify for Songs:**
   - The script searches Spotify for each song on the Billboard Hot 100 list.
   - It collects the Spotify URI for each song found.

4. **Create a Spotify Playlist:**
   - The script creates a new private playlist on your Spotify account, named after the specified date.

5. **Add Songs to Playlist:**
   - The script adds the collected songs to the newly created Spotify playlist.

## Steps to Run the Project

1. **Set Up Spotify Developer Account:**
   - Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/login).
   - Log in with your Spotify account.
   - Click on `Create an App`.
   - Fill in the required details and click `Create`.
   - Copy your `Client ID`, `Client Secret`, and set a `Redirect URI` (e.g., `http://localhost:8888/callback`).

2. **Run the Script:**
   - Replace the placeholder values in the script with your Spotify credentials:
     ```python
     sp = spotipy.Spotify(
         auth_manager=SpotifyOAuth(
             scope="playlist-modify-private",
             redirect_uri="your redirect url",
             client_id="your client id",
             client_secret="your client secret",
             show_dialog=True,
             cache_path="token.txt"
         )
     )
     ```
   - Save and run the script.

3. **Follow the Prompts:**
   - Enter the date for which you want to create the playlist (in `YYYY-MM-DD` format).
   - Log in to your Spotify account when prompted and authorize the application.
   - The script will create a new private playlist and add the Billboard Hot 100 songs for the specified date.

## Example

1. **Input Date:**
   - The script will prompt: `Which year do you want to travel to? Type the date in this format YYYY-MM-DD:`
   - Enter a date, e.g., `2023-06-10`.

2. **Output:**
   - The script will create a new private playlist named `2023-06-10 Billboard 100` on your Spotify account.
   - It will add all the songs from the Billboard Hot 100 list for the specified date to the playlist.

---
