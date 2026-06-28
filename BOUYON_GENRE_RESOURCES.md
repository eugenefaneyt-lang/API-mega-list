# 🎵 YouTube Bouyon Genre Resources & APIs

**A comprehensive guide to gathering Bouyon music data from YouTube and related platforms**

---

## 📚 Table of Contents

- [Overview](#overview)
- [YouTube-Based APIs](#youtube-based-apis)
- [Music Metadata APIs](#music-metadata-apis)
- [Multi-Platform Video APIs](#multi-platform-video-apis)
- [Getting Started Examples](#getting-started-examples)
- [Key Search Terms](#key-search-terms)
- [Popular Bouyon Artists & Channels](#popular-bouyon-artists--channels)

---

## Overview

**Bouyon** is a music genre that originated in **Dominica**, known for its energetic rhythm and cultural significance in the Caribbean. This resource guide provides developers, researchers, and enthusiasts with comprehensive information on how to gather, analyze, and integrate Bouyon music data from YouTube and other platforms.

### What is Bouyon?
- **Origin**: Dominica (Caribbean island)
- **Characteristics**: Fast-paced, rhythmic, party music
- **Cultural Significance**: Part of Caribbean musical heritage
- **Popularity**: Growing presence on YouTube and streaming platforms

---

## YouTube-Based APIs

### 1. **YouTube Data API v3** ⭐ (Official API)
**Official Google API for accessing YouTube content**

**Documentation**: [YouTube Data API v3 Docs](https://developers.google.com/youtube/v3)

#### Key Endpoints for Bouyon:

| Endpoint | Purpose | Use Case |
|----------|---------|----------|
| `/search` | Search for Bouyon videos | Find all Bouyon music, covers, mixes |
| `/videos` | Get video metadata | Retrieve details about specific Bouyon videos |
| `/playlists` | Access playlists | Find curated Bouyon music playlists |
| `/playlistItems` | Get playlist contents | Extract all videos from Bouyon playlists |
| `/channels` | Artist/label channels | Follow Bouyon music producers and labels |
| `/captions` | Video transcripts | Extract lyrics and spoken content |

#### Sample Search Query:
```
Search Query: "bouyon music"
Alternative Queries:
- "Bouyon Dominica"
- "Bouyon mix"
- "Bouyon dance"
- "Bouyon party"
- "Bouyon band"
- "WCK bouyon" (Popular band)
```

#### Python Example:
```python
import requests

API_KEY = "YOUR_YOUTUBE_API_KEY"
SEARCH_URL = "https://www.googleapis.com/youtube/v3/search"

params = {
    "key": API_KEY,
    "part": "snippet",
    "q": "bouyon music",
    "type": "video",
    "order": "relevance",
    "maxResults": 50,
    "region": "DM"  # Dominica region code (optional)
}

response = requests.get(SEARCH_URL, params=params)
results = response.json()

for item in results.get('items', []):
    print(f"Title: {item['snippet']['title']}")
    print(f"Channel: {item['snippet']['channelTitle']}")
    print(f"Video ID: {item['id']['videoId']}")
    print("---")
```

#### Feature Collections:
- Video metadata (title, description, view count, likes)
- Channel information
- Transcript/captions (when available)
- Upload dates and statistics
- Thumbnail images

---

### 2. **YouTube Transcript Scraper APIs**
**Extract transcripts, captions, and subtitles from YouTube videos**

#### Use Cases for Bouyon:
- Extract song lyrics and translations
- Get transcripts from documentary videos about Bouyon
- Analyze spoken content in Bouyon interviews
- Create searchable databases of Bouyon music content

#### Popular APIs:
- **🌟 Youtube Transcript Scraper** - $0.5 per 1k videos
- **🎙 Video Transcript - YouTube, TikTok, Instagram & More** - Multi-platform support
- **🎬 YouTube Video Captions Scraper** - Extract auto-generated subtitles in multiple languages

---

### 3. **YouTube Playlist & Channel Scrapers**
**Extract data from Bouyon playlists and artist channels**

#### APIs:
- **✨ Free Youtube Playlist Scraper** - Extract playlist structure and metadata
- **🎬 Youtube Playlist Extractor** - Get complete playlist information
- **🏯 Youtube Channel Scraper** - Extract channel videos and statistics
- **🏯 Youtube Playlist Scraper (Pay Per Result)** - High-volume playlist data

#### What You Can Extract:
- All videos from Bouyon playlists
- Video order and organization
- Playlist metadata and descriptions
- Channel subscriber counts and statistics
- Upload frequency and patterns

---

### 4. **YouTube Comments & Engagement Scrapers**
**Analyze audience engagement with Bouyon content**

#### APIs:
- **💬 YouTube Comments Scraper** - Extract comments from Bouyon videos
- **🏯 Tiktok Comments Scraper** - For cross-platform analysis

#### Data Points:
- Comment text and sentiment
- User engagement metrics
- Community discussions about Bouyon
- Trending topics within Bouyon community
- Hashtag usage and trends

---

### 5. **YouTube Video Download & Conversion Tools**
**Archive and convert Bouyon music content**

#### APIs:
- **🎵 YouTube Audio/MP3 Downloader** - Extract audio from Bouyon videos
- **🎉 YouTube Long Video Downloader** - Download Bouyon DJ mixes and sets
- **📹 YouTube Video Downloader** - Download videos in various formats
- **🎬 YouTube Video Formats Scraper** - Extract technical video specifications

#### Features:
- Download in multiple audio formats (MP3, M4A, WEBM)
- Preserve multiple language tracks
- Bulk download capabilities
- Direct download links

---

## Music Metadata APIs

### 1. **Genius API** 🎤 (Lyrics & Metadata)
**Music intelligence platform for lyrics and artist information**

**Documentation**: [Genius API Docs](https://docs.genius.com/)

#### Use Cases:
- Extract Bouyon song lyrics
- Get artist biographical information
- Find song production credits
- Track featured artists and collaborations

#### Features:
- Lyrics with timestamps
- Artist profiles and images
- Album information
- Production and songwriting credits
- Historical data about Bouyon as a genre

#### Python Example:
```python
import requests

GENIUS_API_TOKEN = "YOUR_GENIUS_API_TOKEN"
headers = {"Authorization": f"******"}

search_query = "bouyon music"
search_url = "https://api.genius.com/search"

params = {
    "q": search_query,
    "per_page": 50,
    "page": 1
}

response = requests.get(search_url, headers=headers, params=params)
data = response.json()

for hit in data['response']['hits']:
    song = hit['result']
    print(f"Song: {song['title']}")
    print(f"Artist: {song['primary_artist']['name']}")
    print(f"URL: {song['url']}")
    print("---")
```

---

### 2. **MusicBrainz API** 🎼 (Open Music Database)
**Free, open-source music metadata database**

**Documentation**: [MusicBrainz API](https://musicbrainz.org/doc/MusicBrainz_API)

#### Use Cases:
- Find comprehensive metadata about Bouyon artists
- Track album releases and versions
- Get ISRC codes for Bouyon songs
- Access crowdsourced music information

#### Features:
- Artist discographies
- Release information
- Recording metadata
- ISRC and catalog numbers
- Genre classification

#### Bouyon Artists in MusicBrainz:
- Search for prominent Bouyon bands and solo artists
- Collect discography information
- Track collaborations

---

### 3. **Spotify Web API** 🎧 (Limited Bouyon Coverage)
**Access Spotify's music catalog and playlists**

**Documentation**: [Spotify Web API](https://developer.spotify.com/documentation/web-api/)

#### Use Cases:
- Find available Bouyon music on Spotify
- Analyze Bouyon playlists and recommendations
- Get audio feature analysis (BPM, key, energy)
- Track listener demographics

#### Features:
- Search for Bouyon artists and tracks
- Get playlist recommendations
- Audio analysis (tempo, danceability, energy)
- User and follower counts
- Audio preview links

---

### 4. **SoundCloud API** 🎵 (Indie Bouyon Artists)
**Community music platform with more independent Bouyon artists**

**Documentation**: [SoundCloud Developer Portal](https://developers.soundcloud.com/)

#### Use Cases:
- Discover independent Bouyon artists
- Access recordings not on major platforms
- Find remixes and covers
- Track emerging talent

#### Features:
- Artist profiles
- Track metadata and waveforms
- Comments and user interactions
- Playlist and collection information
- Download availability

---

## Multi-Platform Video APIs

### 1. **Apify Platform APIs**
**Specialized web scraping APIs for video platforms**

Popular Apify Actors for Video Content:
- **YouTube Playlist Scraper** - Extract complete playlists
- **YouTube Channel Scraper** - Get all channel videos
- **YouTube Transcript Scraper** - Extract video transcripts
- **Video Downloader** - Multi-platform downloads
- **YouTube Comments Scraper** - Extract community discussions

---

## Getting Started Examples

### Example 1: Gather All Bouyon Videos from YouTube

```python
import requests
import json

def gather_bouyon_videos(api_key, max_results=100):
    """
    Gather Bouyon music videos from YouTube
    """
    search_url = "https://www.googleapis.com/youtube/v3/search"
    
    search_terms = [
        "bouyon music",
        "bouyon dance",
        "bouyon mix",
        "Dominica bouyon",
        "WCK band",
        "bouyon party"
    ]
    
    all_videos = []
    
    for term in search_terms:
        params = {
            "key": api_key,
            "part": "snippet",
            "q": term,
            "type": "video",
            "maxResults": min(50, max_results),
            "order": "relevance"
        }
        
        response = requests.get(search_url, params=params)
        results = response.json()
        
        for item in results.get('items', []):
            video = {
                "title": item['snippet']['title'],
                "channel": item['snippet']['channelTitle'],
                "video_id": item['id']['videoId'],
                "published_at": item['snippet']['publishedAt'],
                "description": item['snippet']['description'],
                "thumbnail": item['snippet']['thumbnails']['default']['url'],
                "search_term": term
            }
            all_videos.append(video)
    
    return all_videos

# Usage:
# videos = gather_bouyon_videos("YOUR_API_KEY")
# with open("bouyon_videos.json", "w") as f:
#     json.dump(videos, f, indent=2)
```

---

### Example 2: Extract Lyrics and Metadata Using Genius API

```python
import requests

def get_bouyon_song_data(genius_token):
    """
    Get Bouyon song data from Genius API
    """
    headers = {"Authorization": f"******"}
    search_url = "https://api.genius.com/search"
    
    search_queries = [
        "bouyon",
        "bouyon Dominica",
        "Caribbean bouyon",
        "WCK bouyon"
    ]
    
    songs = []
    
    for query in search_queries:
        params = {
            "q": query,
            "per_page": 50,
            "page": 1
        }
        
        response = requests.get(search_url, headers=headers, params=params)
        data = response.json()
        
        for hit in data['response']['hits']:
            result = hit['result']
            song = {
                "title": result['title'],
                "artist": result['primary_artist']['name'],
                "url": result['url'],
                "image": result['song_art_image_url'],
                "stats": {
                    "pageviews": result.get('stats', {}).get('pageviews', 0)
                }
            }
            songs.append(song)
    
    return songs
```

---

### Example 3: Create a Bouyon Music Database

```python
import requests
import sqlite3
from datetime import datetime

def create_bouyon_database():
    """
    Create a SQLite database for Bouyon music data
    """
    conn = sqlite3.connect('bouyon_music.db')
    cursor = conn.cursor()
    
    # Create videos table
    cursor.execute('''
        CREATE TABLE IF NOT EXISTS videos (
            id INTEGER PRIMARY KEY,
            youtube_id TEXT UNIQUE,
            title TEXT,
            channel TEXT,
            published_at TEXT,
            description TEXT,
            view_count INTEGER,
            like_count INTEGER,
            comment_count INTEGER,
            created_at TIMESTAMP
        )
    ''')
    
    # Create artists table
    cursor.execute('''
        CREATE TABLE IF NOT EXISTS artists (
            id INTEGER PRIMARY KEY,
            name TEXT UNIQUE,
            genre TEXT,
            origin TEXT,
            description TEXT,
            youtube_channel_id TEXT,
            followers INTEGER,
            created_at TIMESTAMP
        )
    ''')
    
    # Create playlists table
    cursor.execute('''
        CREATE TABLE IF NOT EXISTS playlists (
            id INTEGER PRIMARY KEY,
            playlist_id TEXT UNIQUE,
            title TEXT,
            description TEXT,
            channel TEXT,
            video_count INTEGER,
            created_at TIMESTAMP
        )
    ''')
    
    conn.commit()
    conn.close()
    
    return 'bouyon_music.db'

# Usage:
# create_bouyon_database()
```

---

## Key Search Terms

### Primary Search Terms:
- `bouyon music`
- `bouyon dance`
- `bouyon mix`
- `Dominica bouyon`
- `bouyon party`

### Artist/Band Names:
- `WCK band`
- `First Serenade`
- `Bouyon classics`
- `Dominica music`
- `Caribbean bouyon`

### Content Types:
- `bouyon live`
- `bouyon DJ mix`
- `bouyon covers`
- `bouyon tutorials`
- `bouyon history`

### Hashtags (for TikTok/Instagram):
- `#bouyon`
- `#bouyon2024`
- `#DominicaBouyon`
- `#BouPM` (Bouyon + Caribbean locations)
- `#CaribbeanMusic`

---

## Popular Bouyon Artists & Channels

### Notable Artists:
- **WCK** - Pioneering Bouyon band
- **First Serenade** - Popular Bouyon group
- **Bouyon Kings** - Contemporary performers
- **Dominica Music Collective** - Various artists

### Key YouTube Channels:
- Bouyon Music Official
- Caribbean Music Hub
- Dominica Entertainment
- Bouyon Classics Archive
- DJ Bouyon Mixes

*(Note: Channel URLs and artist profiles should be verified on YouTube)*

---

## API Comparison Table

| API | Best For | Cost | Rate Limits | Data Format |
|-----|----------|------|-------------|------------|
| YouTube Data API v3 | Comprehensive YouTube data | Free/Paid | 10,000 quota units/day | JSON |
| Genius API | Lyrics & metadata | Free | 20 requests/second | JSON |
| MusicBrainz API | Artist/album metadata | Free | 1 request/second | JSON/XML |
| Spotify API | Streaming data | Free/Paid | 429 limit per auth flow | JSON |
| SoundCloud API | Independent artists | Free/Paid | Variable | JSON |
| Apify APIs | Platform scraping | Paid | Platform dependent | JSON/CSV |

---

## Best Practices

### 1. API Usage
- **Rate Limiting**: Respect API rate limits to avoid blocking
- **Caching**: Cache results to reduce API calls
- **Attribution**: Always credit content creators and artists
- **Terms of Service**: Comply with each platform's TOS

### 2. Data Collection
- **Legal Compliance**: Ensure compliance with copyright and data collection laws
- **User Privacy**: Never collect personal user data without consent
- **Content Quality**: Verify data accuracy and completeness
- **Updates**: Regularly refresh data to maintain accuracy

### 3. Content Handling
- **Artist Rights**: Respect artist intellectual property
- **Fair Use**: Ensure your use case falls under fair use if applicable
- **Attribution**: Always provide proper credit and links
- **Licensing**: Understand licensing requirements for music content

---

## Resources & Links

### Documentation
- [YouTube Data API v3 Documentation](https://developers.google.com/youtube/v3)
- [Genius API Documentation](https://docs.genius.com/)
- [MusicBrainz API Documentation](https://musicbrainz.org/doc/MusicBrainz_API)
- [Spotify Web API](https://developer.spotify.com/documentation/web-api/)

### Related Tools
- [Apify Platform](https://apify.com/)
- [YouTube Data API Console](https://console.developers.google.com/)
- [Genius Developer Portal](https://genius.com/api-clients)

### Communities
- [Bouyon Music Community](https://musicbrainz.org/genre/bouyon) (MusicBrainz)
- [YouTube Music Community](https://www.youtube.com/howyoutubeworks)
- [Caribbean Music Forums](https://www.caribbeanmusic.com/)

---

## Contributing

If you have additional resources, APIs, or information about Bouyon music and YouTube data collection, please contribute to this guide!

---

## License

This resource guide is provided as-is for educational and development purposes. Always respect copyright, licensing, and terms of service agreements for all APIs and platforms mentioned.

---

**Last Updated**: 2026-06-28
**Maintainer**: API Mega List Community
