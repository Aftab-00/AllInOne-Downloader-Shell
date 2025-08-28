

# AllInOne Downloader Shell

A powerful, cross-platform command-line download manager and media toolkit. Effortlessly download videos, music, images, torrents, and more from dozens of sources — all in one elegant shell script.

---

## Key Features
- **Universal Downloader**: YouTube, Spotify, SoundCloud, Vimeo, Instagram, TikTok, Bandcamp, GitHub, and more.
- **Video & Audio Extraction**: Download in multiple formats and qualities (MP3, M4A, FLAC, Opus, 1080p, 720p, etc.).
- **Playlist & Album Support**: Batch download playlists and albums from supported platforms.
- **Torrent & Magnet Link Support**: Full torrent client functionality with seeding options.
- **Image & Gallery Downloads**: Grab images and galleries from popular social sites.
- **Streaming**: Instantly stream audio from videos or playlists.
- **Auto-Update & Dependency Management**: Self-updating script and automated dependency installation.
- **Customizable Download Directory**: Choose or set your preferred download location.
- **Logging & Configuration**: Robust logging and easy configuration management.
- **Cross-Platform**: Works on Linux, macOS, Termux (Android), and Windows (via Git Bash/Cygwin).
- **Advanced Features**: Proxy support, rate limiting, custom format selection, and more.

---

## Quick Start
### 1. Clone the Repository
```bash
git clone https://github.com/Aftab-00/AllInOne-Downloader-Shell.git
cd AllInOne-Downloader-Shell
```

### 2. Run the Script
```bash
chmod +x AllInOne-Downloader-Shell.sh
./AllInOne-Downloader-Shell.sh
```

> **Tip**: The script will auto-install itself to your `$HOME/bin` directory for easy access.

---

## Installation & Requirements
- **Linux / macOS / Termux**: No manual setup required — dependencies are auto-installed.
- **Windows**: Use [Git Bash](https://gitforwindows.org/) or [Cygwin](https://www.cygwin.com/). Ensure Python, ffmpeg, and curl are installed.

### Supported Dependencies (auto-installed):
- `yt-dlp`, `spotdl`, `gallery-dl`, `ffmpeg`, `aria2`, `curl`, `wget`, `mpv`, `python3`, `pip3`

---

## Supported Platforms
- **YouTube**: videos, playlists, shorts, audio, subtitles
- **Spotify**: tracks, playlists, albums
- **SoundCloud**
- **Instagram, Pinterest, Imgur, TikTok**: images/videos
- **Vimeo, Dailymotion, Twitch**
- **Bandcamp**
- **GitHub**: repo cloning
- **Torrent & Magnet Links**: Full torrent client with seeding options
- **Direct File Downloads**

---

## Usage
### Basic Usage
1. Launch the script:  
   `./AllInOne-Downloader-Shell.sh`
2. Choose your download source and method from the menu.
3. Paste the URL and select your preferred format/quality.
4. Enjoy your downloaded content!

### Advanced Usage
```bash
# Direct download with URL
./AllInOne-Downloader-Shell.sh "https://youtube.com/watch?v=example"

# Download with specific options
./AllInOne-Downloader-Shell.sh --format mp3 --quality best "https://youtube.com/watch?v=example"

# Batch download from file
./AllInOne-Downloader-Shell.sh --batch urls.txt

# Use custom configuration
./AllInOne-Downloader-Shell.sh --config /path/to/custom.conf
```

### Command-Line Options
| Option | Description |
|--------|-------------|
| `--config FILE` | Use custom configuration file |
| `--format FMT` | Specify output format (mp3, mp4, etc.) |
| `--quality Q` | Set quality (best, worst, 1080p, etc.) |
| `--output DIR` | Set custom output directory |
| `--batch FILE` | Batch download URLs from file |
| `--proxy URL` | Use proxy for downloads |
| `--no-update` | Disable auto-update for this session |
| `--debug` | Enable debug mode |
| `--help` | Show help information |

---

## Configuration
All settings are stored in:  
`~/.config/allinone-dl/config.conf`

Logs are saved to:  
`~/.config/allinone-dl/download.log`

### Configuration Options
```ini
# Default download directory
DEFAULT_PATH=~/Aftab-DL

# Enable/disable auto-update
AUTO_UPDATE=true

# Enable/disable logging
LOGGING=true

# Enable/disable debug mode
DEBUG=false

# Proxy settings (if needed)
PROXY=

# Rate limiting (requests per second)
RATE_LIMIT=

# Concurrent download segments
CONCURRENT_SEGMENTS=4

# Torrent settings
TORRENT_SEED_TIME=60
TORRENT_MAX_CONNECTIONS=16
```

### Environment Variables
You can also configure the script using environment variables:
```bash
export ALLINONE_DOWNLOAD_DIR=~/Downloads
export ALLINONE_AUTO_UPDATE=false
export ALLINONE_PROXY=http://proxy.example.com:8080
```

---

## Torrent & Magnet Link Support
The script includes full torrent client functionality with configurable options:

### Features
- Download from magnet links
- Download .torrent files
- Configurable seeding time
- Adjustable connection limits
- Detailed progress tracking

### Usage
1. Select "Download from URL" from the main menu
2. Enter your magnet link or .torrent URL
3. Choose your preferred download option:
    - "Download torrent (magnet link)" - Quick download without seeding
    - "Download torrent file" - Download .torrent files
    - "Download torrent with seeding" - Download and seed for configured time

### Configuration
Adjust torrent settings in the configuration file:
```ini
# Time to seed after download completion (in seconds)
TORRENT_SEED_TIME=60

# Maximum connections per server
TORRENT_MAX_CONNECTIONS=16
```

---

## Troubleshooting
### Common Issues
1. **"Not a valid URL" Error**
    - Ensure the URL is complete and correctly formatted
    - Check for extra quotes in the URL
    - Enable debug mode for more information

2. **Download Failures**
    - Check your internet connection
    - Verify the URL is accessible in a browser
    - Try updating dependencies
    - Check log files for error details

3. **Permission Errors**
    - Ensure you have write permissions in the download directory
    - Try running with appropriate permissions

4. **Dependency Issues**
    - The script will prompt to install missing dependencies
    - Ensure your package manager is up to date
    - For manual installs, verify all dependencies are installed

### Debug Mode
Enable debug mode to get detailed information:
1. Run the script
2. Select "Toggle debug mode" from the main menu
3. Try your download again
4. Check the log file for detailed output

### Log Analysis
Analyze logs for patterns and issues:
```bash
# View recent errors
tail -f ~/.config/allinone-dl/download.log | grep ERROR

# Filter for specific download types
grep "youtube.com" ~/.config/allinone-dl/download.log

# Analyze success rates
grep -c "Download completed successfully" ~/.config/allinone-dl/download.log
```

---

## Contributing
We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Add tests for new functionality
5. Ensure all tests pass
6. Commit your changes (`git commit -m 'Add amazing feature'`)
7. Push to the branch (`git push origin feature/amazing-feature`)
8. Open a Pull Request

### Development Guidelines
- Follow the existing code style
- Use 4 spaces for indentation
- Add comments for complex functionality
- Keep functions small and focused
- Use descriptive variable names

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Disclaimer
This tool is intended for educational purposes only. Use responsibly and respect copyright laws. The authors are not liable for misuse.

---

## Show Off
- One script. All downloads. Zero hassle.
- Automated, fast, and reliable.
- Your all-in-one media toolkit.

---

## Contact & Support
- **GitHub Issues**: [Open an issue](https://github.com/Aftab-00/AllInOne-Downloader-Shell/issues)

---

## Acknowledgments
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) - YouTube downloader
- [spotdl](https://github.com/spotDL/spotify-downloader) - Spotify downloader
- [gallery-dl](https://github.com/mikf/gallery-dl) - Image gallery downloader
- All contributors and users who make this project better every day.