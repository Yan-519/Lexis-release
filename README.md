# Lexis
A cross-platform word guessing game built with C# and .NET MAUI. Lexis is inspired by Wordle, offering engaging gameplay with multiple word lengths, timed challenges, and a competitive leaderboard system.

## Overview

Lexis is a mobile application that challenges players to guess secret words within a limited number of attempts. The game features:

- 🎮 **Multiple Game Modes**: Play with 3, 4, 5, or 6 letter words
- ⏱️ **Timed Challenges**: Optional time-limited gameplay
- 🌍 **Multi-Language Support**: English and Hebrew (extensible)
- 🏆 **Leaderboard**: Track your performance against other players
- 💰 **Scoring System**: Earn points and currency for achievements
- 🔐 **User Authentication**: Firebase-based login and registration
- 🎯 **Word Finder Tool**: Look up words by length and pattern

## Features

### Core Gameplay
- **Guess the Secret Word**: Players have a limited number of attempts to guess a randomly selected word
- **Letter State Feedback**: Each guess provides visual feedback:
  - ✅ Green: Correct letter in correct position
  - 🟡 Yellow: Correct letter in wrong position
  - ⚪ Gray: Letter not in word
  - 🔵 Blue: Special hint letters
- **Word Validation**: Only valid dictionary words are accepted
- **Attempt Tracking**: Track your attempts and game progress

### Game Modes
- **Classic Mode (5 letters)**: The standard game experience
- **6 Letters**: Extended difficulty for experienced players
- **4 Letters**: Quick games with shorter words
- **3 Letters**: Mini games for fast-paced play
- **Timed Mode**: Optional countdown timer (1-300 seconds) for added challenge

### User Features
- **Player Profiles**: Registration and login via Firebase
- **Score Tracking**: Monitor your cumulative score
- **In-Game Currency**: Earn "money" for achievements and use it in the shop
- **Settings**: Customize language preferences
- **Leaderboard**: View top players and compete globally

### Additional Tools
- **Word Finder**: Search for words by:
  - Word length (3-6 letters)
  - Language (English/Hebrew)
  - Partial patterns or specific letters
- **Answer Page**: Quick access to word solutions and hints

## Technical Stack

### Framework & Platform
- **Framework**: .NET MAUI (Multi-platform App UI)
- **Language**: C# 12 (preview features enabled)
- **Target Platforms**: 
  - Android 10.0+ (API 21+)
  - Windows 10/11 (net10.0-windows)

### Key Dependencies
- **Firebase**:
  - `FirebaseAuthentication.net` - User authentication
  - `FirebaseDatabase.net` - Real-time data storage
- **UI/UX**:
  - `CommunityToolkit.Maui` - Additional MAUI controls
  - `Microsoft.Toolkit.Uwp.Notifications` - Windows notifications
  - `Plugin.LocalNotification` - Cross-platform local notifications
- **Data Handling**:
  - `Newtonsoft.Json` - JSON serialization
  - `System.Formats.Nrbf` - Binary format support
  - `System.Drawing.Common` - Drawing utilities

### Project Structure
```
Lexis/
├── Models/              # Game logic and state management
│   └── Lexis_model.cs  # Core word guessing logic
├── Storage/            # Data storage and language definitions
│   └── Lexis_data.cs   # Keyboard layouts, constants
├── Management/         # User and game management
├── Pages/              # UI pages
│   ├── Home_page.xaml  # Main menu
│   ├── Game_page.xaml  # Game interface
│   ├── Leaderboard_page.xaml
│   ├── Settings_page.xaml
│   └── Answer_page.xaml
├── Platforms/          # Platform-specific implementations
│   ├── Android/
│   └── Windows/
└── Resources/          # Assets, fonts, images
```

## Installation

### Requirements
- .NET 10.0 SDK or later
- Visual Studio 2024 or Visual Studio Code with C# extension
- For Android: Android SDK (API 21+)
- For Windows: Windows 10/11

## Usage

### Starting a Game
1. Launch the app and log in with your Firebase account
2. From the home screen, select your preferred word length (3-6 letters)
3. Optionally enable **"Play limited time"** and adjust the time limit
4. Tap the selected difficulty to start

### Playing
- Tap on the on-screen keyboard to guess letters
- Use the ⌫ key to delete letters
- Submit your guess when you have a complete word
- Analyze the color feedback and make your next guess
- Win by finding the secret word or lose if attempts run out

### Accessing Features
- **⚙️ Settings** (top-left): Change language preferences
- **👤 User Info** (bottom): View profile and stats
- **🏆 Leaderboard** (bottom-center): Check rankings
- **🔍 Word Finder** (bottom-right): Search for words

## Game Mechanics

### Attempts & Win/Loss
- **Standard Attempts**: Typically 6 attempts per game (configurable)
- **Win Condition**: Guess the word before running out of attempts
- **Lose Condition**: Exhaust all attempts without guessing correctly

### Scoring System
- Points are awarded based on:
  - Number of attempts used
  - Word difficulty (word length)
  - Speed (in timed mode)
- Currency ("money") can be earned for purchases

### Multi-Language Support
- **Keyboard Layout**: Supports different keyboard layouts:
  - QWERTY (English)
  - Hebrew characters with Hebrew layout
- **Words Database**: Separate word lists per language
- Easy to extend with additional languages

## Configuration

### Customizable Settings
- **Game Time Limit**: 1-300 seconds (60 seconds default)
- **Language**: English or Hebrew
- **Platform-Specific**: Separate configs for Android, Windows

### Firebase Configuration
Ensure your Firebase project is configured in the app with:
- Authentication enabled
- Realtime Database setup
- Proper security rules for user data

## Development Notes

### Building Executables
The project uses PyInstaller-style compilation for some platforms. Platform-specific build outputs:
- Android: APK format (debug builds with embedded assemblies disabled)
- Windows: .NET Native or standard executable

### Advanced Features
- **Unsafe blocks enabled** for performance-critical operations
- **Nullable reference types** enabled for type safety
- **Preview C# features** (LangVersion=preview) for cutting-edge functionality

## Troubleshooting

### Common Issues

**Firebase Connection Failed**
- Update to the latest version
- Verify Firebase credentials are correctly configured
- Check internet connection
- Ensure Firebase project has proper security rules

**Game Not Starting**
- Clear app cache and restart
- Verify user authentication is successful
- Check that word lists are loaded properly

**Performance Issues on Android**
- `EmbedAssembliesIntoApk` is disabled to reduce initial load time
- For production, consider enabling trimming and optimization

## License

This project is provided as-is for personal and educational use.

## Author

**Yan-519**

## Support & Contribution

Not up-to-date versions could no longer be supported and won't work.

---

**Version**: 5.0  
**Language**: C# (100%)  
**Repository**: Yan-519/Lexis  
**Status**: Active Development
