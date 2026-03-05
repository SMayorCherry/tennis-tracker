# Tennis Performance Tracker

A comprehensive mobile app to track tennis players' performance during matches with detailed statistics and analysis.

## Features

### Core Tracking
- **Real-time Match Scoring**: Track sets, games, and points with tennis scoring rules
- **Performance Statistics**: Monitor key performance indicators during play
- **Match History**: View past matches and performance trends

### Performance Counters
1. **First Serve Faults** - Track serving accuracy
2. **Double Faults** - Monitor double fault occurrences
3. **Aces** - Count successful aces
4. **Baseline Winners** - Track winning shots from baseline
5. **Volley Winners** - Count successful volleys
6. **Drop Shots** - Monitor tactical shot placement
7. **Lobs** - Track lob shot usage
8. **Game Score** - Automatic tennis scoring (0, 15, 30, 40, Deuce, Advantage)
9. **Set Score** - Best of 3 sets with proper tennis rules

### Match Analysis
- **Performance Insights**: AI-generated insights based on statistics
- **Detailed Summary**: Comprehensive match breakdown
- **Visual Statistics**: Color-coded performance metrics
- **Match Duration**: Automatic time tracking

## Installation

### Prerequisites
- Node.js (v16 or higher)
- React Native development environment
- Android Studio (for Android) or Xcode (for iOS)

### Setup
1. Clone or download the project
2. Install dependencies:
   ```bash
   npm install
   ```

3. For iOS (Mac only):
   ```bash
   cd ios && pod install
   ```

4. Run the app:
   ```bash
   # For Android
   npm run android
   
   # For iOS
   npm run ios
   ```

## Usage

### Starting a Match
1. Enter player names on the home screen
2. Tap "Start Match" to begin tracking
3. Use the point buttons to update scores
4. Tap performance counters as actions occur during play

### During Match Play
- **Scoring**: Tap the +1 buttons for each player to update points
- **Statistics**: Tap the colored stat buttons to increment counters
- **Real-time Updates**: Score automatically updates following tennis rules

### Match Completion
- Match ends automatically when a player wins 2 sets
- Manual finish option available
- Automatic save to match history
- Immediate access to detailed summary

### Viewing History
- All completed matches saved locally
- Tap any match in history to view detailed summary
- Performance insights and recommendations

## Technical Details

### Built With
- **React Native 0.72.6** - Cross-platform mobile development
- **React Navigation** - Screen navigation
- **AsyncStorage** - Local data persistence
- **React Native Vector Icons** - Icon support

### Architecture
- Component-based architecture
- State management with React hooks
- Local storage for match persistence
- Responsive mobile design

### Tennis Scoring Rules
- Points: 0, 15, 30, 40, Deuce, Advantage
- Games: First to win 6 games with 2-game lead
- Sets: Best of 3 sets
- Automatic progression through scoring levels

## Performance Statistics

### Serving Metrics
- **Aces**: Direct service winners
- **First Serve Faults**: Failed first serves
- **Double Faults**: Two consecutive faults

### Shot Quality
- **Baseline Winners**: Winning shots from back court
- **Volley Winners**: Successful net play
- **Drop Shots**: Short tactical shots
- **Lobs**: Defensive/offensive high shots

### Analysis Features
- Performance insights based on statistics
- Serving accuracy assessment
- Court coverage analysis
- Shot variety evaluation
- Tactical recommendations

## Data Storage
- All data stored locally on device
- No internet connection required
- Match history preserved between app sessions
- Privacy-focused design

## Future Enhancements
- Export match data
- Advanced analytics
- Player comparison
- Tournament mode
- Cloud backup
- Video analysis integration

## Development

### Project Structure
```
src/
├── App.js              # Main app component
├── screens/
│   ├── HomeScreen.js   # Home and match history
│   ├── MatchScreen.js  # Live match tracking
│   └── SummaryScreen.js # Match analysis
└── [Additional components as needed]
```

### Key Components
- **HomeScreen**: Player input and match history
- **MatchScreen**: Real-time tracking interface
- **SummaryScreen**: Post-match analysis and insights

## License
This project is created for educational and personal use.

## Support
For issues or questions, please refer to the React Native documentation or create an issue in the project repository. 