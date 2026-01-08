# AvatarDownloader Module for Hikka Userbot

## Overview
AvatarDownloader is a versatile module for Hikka (based on Telethon) that allows users to download profile pictures (avatars) from Telegram users, chats, or channels. It supports downloading specific avatars by number, random selection, and handles both static images and video/emoji avatars. Perfect for archiving, sharing, or analyzing profile media.

This module is designed for Telegram userbots and integrates seamlessly with the Hikka framework. It uses FFmpeg for video processing to ensure compatibility with Telegram's media upload requirements.

**Version:** 1.1.9  
**Developer:** [@lolotol89](https://t.me/lolotol89)  
**Repository:** [https://github.com/lolotol/Mods/tree/main/AvatarDownloader] 

## Features
- **Download User Avatars by Number:** Fetch a specific profile photo from a user's history (e.g., the 5th avatar).
- **Random Avatar Selection:** Pick and download a random avatar from a user's profile photos.
- **Chat/Channel Avatars:** Download the current avatar of any chat or channel.
- **Video/Emoji Avatar Support:** Handles animated (video) and emoji-based avatars, converting them for proper upload/viewing in Telegram.
- **Error Handling:** User-friendly messages for cases like no avatars available, invalid numbers, or download failures.
- **Temporary File Management:** Automatically cleans up temp files after processing.
- **Localization:** All user-facing strings are in Russian with emojis for better UX.

## Commands
- `.getava [number] [username/reply]`: Download a specific avatar by number from a user or the current chat/channel avatar. If no number, defaults to 1.
- `.getmyava [number]`: Download your own avatar by number (defaults to 1).
- `.randomava [username/reply]`: Download a random avatar from a user (or yourself if no target).
- `.randommyava`: Download a random avatar from your own profile.

## Installation
1. **Prerequisites:**
   - Hikka Userbot installed and running.
   - FFmpeg installed on your system (for video avatar processing).
   - Telethon library (already included in Hikka).

2. **Steps:**
   - Download the module file (`AvatarDownloader.py`) from this repository.
   - Place it in your Hikka modules directory (usually `~/.hikka/modules/` or similar).
   - Restart Hikka or load the module via `.loadmod` command.
   - Ensure FFmpeg is in your system's PATH for video handling.

Example in Hikka:
```
.dlmod https://github.com/lolotol/Mods/blob/main/AvatarDownloader/AvatarDownloader.py
```

## Usage Examples
- Download the 3rd avatar from a user: `.getava 3 @username`
- Random avatar from reply: Reply to a message and type `.randomava`
- Your own random avatar: `.randommyava`
- Chat avatar: `.getava` in a chat (no args).

## Known Issues
- Video avatars require FFmpeg; errors may occur if not installed.
- Limited to 100 photos per API call (Telegram limitation), but handles pagination.
- Only works for users with public profile photos.
