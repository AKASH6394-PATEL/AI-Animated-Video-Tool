# 🎬 AI Animated Video Generator

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-FF4B4B.svg)](https://streamlit.io)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A powerful, professional-grade AI-powered video generation tool that creates stunning animated videos with multi-language voiceovers, dynamic text animations, background music, subtitles, overlays, and sound effects. Perfect for content creators, educators, marketers, and social media professionals.

## ✨ Key Features

### 🎤 Advanced Audio
- **Multi-language AI Voiceovers**: 10+ languages including English, Hindi, Spanish, Japanese, Russian, Chinese, French, Tamil, Telugu, and German
- **Voice Speed Control**: Adjust speaking rate from -100% to +100%
- **Background Music**: Add custom music with volume control
- **Sound Effects (SFX)**: Per-scene sound effects support
- **Audio Mixing**: Mix AI voice with original video audio or replace it entirely

### 🎨 Visual Effects
- **Animated Text**: Typewriter and Math (LaTeX) animation styles using Manim
- **Auto-Subtitles**: Automatic caption generation with customizable styling
- **Emoji Overlays**: Add emojis per scene for engagement
- **Highlight Banners**: Custom text banners for emphasizing key moments
- **Ken Burns Effect**: Smooth zoom animations on images
- **Progress Bar**: Optional video progress indicator
- **Logo/Watermark**: Add branded overlays with adjustable opacity and position
- **Custom Colors**: Configurable text and background colors

### 🎬 Two Operating Modes

#### 1. **Scene-by-Scene Mode** (Script-driven)
- Video length = Script length
- Perfect for creating new videos from scratch
- Automatic image search via Pexels API
- Custom image upload support
- B-roll and educational content creation

#### 2. **Video Dubbing Mode** (Video-driven)
- Video length = Uploaded video length
- Ideal for dubbing existing videos
- Preserves original video timing
- Mix or replace original audio
- Professional video localization

### 📤 Export Options
- High-quality MP4 export (1280x720, 24fps)
- Optional 5-second GIF preview
- Download directly from the web interface

## 🛠️ Tech Stack

- **Frontend**: Streamlit
- **AI Voice**: Edge-TTS (Microsoft Edge Text-to-Speech)
- **Animation**: Manim (Mathematical Animation Engine)
- **Video Processing**: MoviePy
- **Image Source**: Pexels API
- **Audio Processing**: AudioFileClip, CompositeAudioClip
- **Additional**: NumPy, asyncio, requests

## 💻 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- FFmpeg (for video processing)

### Step 1: Clone the Repository
```bash
git clone https://github.com/AKASH6394-PATEL/AI-Animated-Video-Tool.git
cd AI-Animated-Video-Tool
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Install FFmpeg

**Windows:**
```bash
# Download from https://ffmpeg.org/download.html
# Add to PATH environment variable
```

**macOS:**
```bash
brew install ffmpeg
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install ffmpeg
```

### Step 4: Get Pexels API Key
1. Visit [Pexels API](https://www.pexels.com/api/)
2. Sign up for a free account
3. Copy your API key
4. Replace `PEXELS_API_KEY` in the code with your key

### Step 5: Create Required Folders
```bash
mkdir -p assets/images assets/audio sfx
```

## 🚀 Usage

### Running the Application
```bash
streamlit run app.py
```

The app will open in your default web browser at `http://localhost:8501`

### Creating Your First Video

#### **Scene-by-Scene Mode:**
1. **Select Mode**: Choose "Scene-by-Scene (Script-driven)"
2. **Add Script**: Enter your script (one sentence per line)
3. **Optional Inputs**:
   - Upload custom images (JPG/PNG)
   - Add intro/outro text
   - Upload background music (MP3)
4. **Customize**:
   - Select voice and language
   - Adjust voice speed
   - Choose animation style
   - Add emojis per scene
   - Configure colors and logo
5. **Generate**: Click "Video Generate Karein" button
6. **Download**: Get your MP4 file

#### **Video Dubbing Mode:**
1. **Select Mode**: Choose "Video Dubbing (Uploaded Video-driven)"
2. **Upload Video**: Add your MP4 file
3. **Add Script**: Enter narration/dialogue (one line per scene)
4. **Audio Options**: Choose to mix or replace original audio
5. **Customize**: Same options as Scene-by-Scene mode
6. **Generate**: Click "Video Generate Karein" button
7. **Download**: Get your dubbed MP4 file

### Advanced Features

#### Adding Sound Effects
1. Place your SFX files (.mp3) in the `sfx/` folder
2. In the "Sound Effects (SFX) Per Scene" box, enter file paths:
   ```
   sfx/applause.mp3
   
   sfx/whoosh.mp3
   ```
3. Leave blank lines for scenes without SFX

#### Using LaTeX Math Animations
1. Select "Math Animation (LaTeX)" as animation style
2. In your script, wrap equations in `$` symbols:
   ```
   $E=mc^2$
   $\int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}$
   ```

## 📝 File Structure

```
AI-Animated-Video-Tool/
├── app.py                 # Main Streamlit application
├── requirements.txt      # Python dependencies
├── README.md             # This file
├── LICENSE               # MIT License
├── .gitignore            # Git ignore file
├── assets/
│   ├── images/          # Downloaded/uploaded images
│   └── audio/           # Generated audio files
├── sfx/                  # Sound effects library
└── media/                # Manim output (temporary)
```

## 🛡️ Troubleshooting

### Common Issues

**Issue**: "FFmpeg not found"
- **Solution**: Install FFmpeg and add to PATH

**Issue**: "Manim render error"
- **Solution**: Check that LaTeX syntax is correct. Use Preview tab to verify.

**Issue**: "Pexels image search failed"
- **Solution**: Verify API key is correct. Check internet connection.

**Issue**: "Video generation is slow"
- **Solution**: Reduce video length, disable progress bar in Video Dubbing mode, use lower resolution images.

**Issue**: "WinError 32: File in use"
- **Solution**: Close all video players. The app handles cleanup automatically.

## 📚 Examples

### Example 1: Educational Video
```python
Script:
Welcome to physics 101
$F=ma$ is Newton's second law
Force equals mass times acceleration
This fundamental equation explains motion

Emojis:
📚
🧮
⚖️
🚀
```

### Example 2: Social Media Content
```python
Script:
Top 5 productivity hacks
Number 5: Use time blocking
Number 4: Eliminate distractions
Number 3: Take regular breaks
Number 2: Prioritize important tasks
Number 1: Start your day early

Banners:
TOP 5
#5
#4
#3
#2
#1
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Akash Patel**
- GitHub: [@AKASH6394-PATEL](https://github.com/AKASH6394-PATEL)
- Email: akashpatel@example.com

## 🚀 Future Enhancements

- [ ] Multiple video quality options (480p, 720p, 1080p, 4K)
- [ ] Batch video generation
- [ ] Cloud storage integration (Google Drive, Dropbox)
- [ ] AI-powered script generation
- [ ] Advanced transition effects
- [ ] Multi-track audio mixing
- [ ] Video templates library
- [ ] Real-time preview
- [ ] Mobile app version
- [ ] API for programmatic access

## ⭐ Show Your Support

Give a ⭐ if this project helped you!

## 💬 Feedback

If you have any feedback, please reach out to me at akashpatel@example.com or open an issue on GitHub.

---

**Made with ❤️ by Akash Patel | 🎬 Creating the future of video generation**
