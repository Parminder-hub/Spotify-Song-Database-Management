# Spotify-Song-Database-Management
# 🎶 Spotify Song Database Management

## 📌 Project Overview

This project aims to create and manage a simulated **Spotify Song Library** using SQL. The database includes essential information about users, songs, playlists, and song play history. The goal is to demonstrate the ability to create complex SQL databases, perform insightful queries, and analyze song and user data for various use cases.

## 🗂️ Database Schema

The database consists of the following tables:

1. **Users Table**: Stores user information.
2. **Songs Table**: Stores information about songs.
3. **Playlists Table**: Stores playlists created by users.
4. **Playlist_Songs Table**: Stores the relationship between playlists and songs.
5. **User_Song_Play_History Table**: Tracks user listening history for song analysis.

### 📊 Table Structure

#### **Users Table**
| Column Name    | Data Type      | Description                      |
|----------------|----------------|----------------------------------|
| user_id        | INT            | Unique user identifier           |
| username       | VARCHAR(100)    | Username of the user             |
| email          | VARCHAR(100)    | Email address                    |
| date_joined    | DATE           | Date the user joined Spotify     |

#### **Songs Table**
| Column Name    | Data Type      | Description                      |
|----------------|----------------|----------------------------------|
| song_id        | INT            | Unique song identifier           |
| title          | VARCHAR(255)    | Title of the song                |
| artist         | VARCHAR(255)    | Artist of the song               |
| album          | VARCHAR(255)    | Album the song is part of        |
| release_date   | DATE           | Release date of the song         |
| duration       | INT            | Duration of the song in seconds  |
| genre          | VARCHAR(50)     | Genre of the song                |
| popularity     | INT            | Popularity score (0-100)         |

#### **Playlists Table**
| Column Name    | Data Type      | Description                      |
|----------------|----------------|----------------------------------|
| playlist_id    | INT            | Unique playlist identifier       |
| playlist_name  | VARCHAR(100)    | Name of the playlist             |
| user_id        | INT            | ID of the user who created it    |
| date_created   | DATE           | Date the playlist was created    |

#### **Playlist_Songs Table**
| Column Name    | Data Type      | Description                      |
|----------------|----------------|----------------------------------|
| playlist_id    | INT            | ID of the playlist               |
| song_id        | INT            | ID of the song                   |

#### **User_Song_Play History Table**
| Column Name    | Data Type      | Description                      |
|----------------|----------------|----------------------------------|
| user_id        | INT            | User ID who listened to the song |
| song_id        | INT            | Song ID played                   |
| play_time      | TIMESTAMP      | Timestamp of when the song was played |

---

## 🔧 SQL Queries

Below are some sample SQL queries that demonstrate the power of the Spotify Song Database:

### 1. **Top 10 Most Popular Songs**
```sql
SELECT title, artist, popularity
FROM Songs
ORDER BY popularity DESC
LIMIT 10;
