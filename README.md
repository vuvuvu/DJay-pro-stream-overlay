# djay Now Playing Overlay

A lightweight, real-time display overlay that shows currently playing track information from djay Pro AI software. Designed specifically for OBS integration and streaming setups.

## Overview

This is a simple HTML-based overlay that reads track information from djay Pro AI's NowPlaying.txt file and displays it in a clean, transparent interface perfect for streaming overlays.

## Features

- **Real-time Track Display**: Shows current track title, artist, album, and duration
- **Automatic Updates**: Monitors the NowPlaying.txt file and updates every second
- **OBS Ready**: Transparent background designed for overlay use
- **Error Handling**: Built-in retry mechanism with graceful error handling
- **Lightweight**: Single HTML file with no external dependencies
- **Mac Compatible**: Works with djay Pro AI's file output system

## Project Structure

```
/djay
├── index.html              # Main overlay interface
├── README.md               # This file
└── djay Media Library.djayMediaLibrary/
    └── NowPlaying.txt      # Track information file (created by djay Pro AI)
```

## Setup

### 1. Configure djay Pro AI
Ensure djay Pro AI is configured to write track information to the NowPlaying.txt file in the djay Media Library folder.

### 2. Host the Files
You have two options:
- **Local File**: Open `index.html` directly in your browser
- **Web Server**: Host the files on a local web server for better file access

### 3. Add to OBS
1. In OBS, add a new "Browser Source"
2. Set the URL to your `index.html` file location
3. Set width: 400px, height: 200px (adjust as needed)
4. The overlay will automatically position itself and display track information

## Technical Details

### File Monitoring
The overlay checks for updates to the NowPlaying.txt file every second using JavaScript's `fetch()` API.

### Error Handling
- Automatic retry mechanism (up to 3 attempts)
- 3-second delay between retry attempts
- Graceful fallback display when file cannot be read

### Display Format
The overlay shows:
- **Title**: Track title
- **Artist**: Artist name
- **Album**: Album name
- **Duration**: Track duration

## Styling

The overlay features:
- Transparent background
- Semi-transparent dark container (rgba(0, 0, 0, 0.7))
- White text with gray labels
- Rounded corners and clean typography
- Positioned at top-left (20px, 20px) by default

## Browser Compatibility

Works with modern browsers that support:
- ES6+ JavaScript (async/await)
- Fetch API
- CSS3

## Troubleshooting

### File Not Found
If you see "Error loading file":
1. Verify djay Pro AI is running and configured to output NowPlaying.txt
2. Check the file path in the JavaScript code matches your djay Media Library location
3. Ensure the browser has permission to access local files (use a web server if needed)

### No Updates
If the display doesn't update:
1. Check the browser console for errors
2. Verify the NowPlaying.txt file is being updated by djay Pro AI
3. Refresh the browser source in OBS

## Customization

You can easily customize the overlay by modifying the CSS in `index.html`:
- Change colors, fonts, and sizing
- Adjust positioning
- Modify the container appearance
- Add animations or transitions

## License

This project is open source and available for personal and commercial use.

    