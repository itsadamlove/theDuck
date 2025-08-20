# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

"The Duck" is a web-based standup meeting tool that randomly selects team members and displays developer jokes to facilitate fun and engaging daily standups. It's a simple vanilla JavaScript application with no build tools or dependencies.

## Architecture

The application consists of three main files:
- **index.html**: Single-page application with containers for the main UI elements
- **theDuck.js**: Core logic handling team member selection, joke display, and UI state management  
- **styles.css**: Responsive styling with animations for emoji rain effects

### Key Components

1. **Team Member Selection System** (theDuck.js:235-251)
   - Maintains arrays of team members and used selections
   - Ensures no duplicate selections until all members have been picked
   - Resets when all team members have been selected

2. **Joke/Fun Fact System** (theDuck.js:9-230)
   - Large arrays of developer jokes and Christmas jokes
   - Random selection without repetition
   - Template replacement for selected team member names

3. **UI State Management**
   - Initial state: Shows title and "Duck Me" button
   - Active state: Displays jokes with selected team member
   - Summary state: Shows celebration screen when all members selected
   - Keyboard support for spacebar/enter navigation

## Development

This is a static site with no build process. To run locally:
1. Open `index.html` directly in a browser
2. Or serve with any static file server (e.g., `python -m http.server`)

The site is deployed via GitHub Pages at: https://itsadamlove.github.io/theDuck/

## Key Functions and Patterns

- **selectRandomUserWithComment()** (theDuck.js:347): Main function triggered by button click
- **randomlySelectValueThatHasNotPreviouslyBeenSelected()** (theDuck.js:235): Core selection logic
- **makeItRain()** (theDuck.js:273): Creates animated emoji effects
- DOM manipulation uses querySelector patterns throughout
- Event handling for both click and keyboard interactions