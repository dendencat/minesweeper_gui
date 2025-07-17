# Minesweeper GUI Project

## Project Overview
This is a Minesweeper game implementation in Rust using the egui/eframe GUI framework. The project is currently in development with several compilation errors that need to be fixed and planned improvements documented in Japanese specifications.

## Current Status

### ✅ COMPLETED: All compilation errors fixed!
The project now builds and runs successfully.

### ✅ IMPLEMENTED FEATURES:
1. **Dynamic Grid System**: Changed from fixed 9x9 grid to Vec<Vec<Cell>> for flexible sizing
2. **Difficulty Levels**: Beginner (9x9, 10 mines), Intermediate (16x16, 40 mines), Expert (30x16, 99 mines)
3. **Enhanced Cell Types**: Added QuestionMark cell type for better gameplay
4. **Game State Management**: Proper state tracking (NotStarted, Playing, Paused, Won, Lost)
5. **First-Click Safety**: Mines are placed after first click to ensure safe start
6. **Improved UI**: 
   - Color-coded numbers (1=blue, 2=green, 3=red, etc.)
   - Mine counter display
   - Timer functionality
   - Visual mine display on game over
   - Flag and question mark support
7. **Better Flagging**: Right-click cycles through Covered → Flagged → QuestionMark → Covered

### Minor Warnings (non-breaking):
- Some unused fields/variants (future features)
- Standard dead code analysis warnings

## Project Structure

```
minesweeper_gui/
├── src/
│   └── main.rs          # Main application code
├── .kiro/
│   └── specs/
│       └── minesweeper-improvement/
│           ├── requirements.md  # Requirements (Japanese)
│           ├── design.md       # Technical design (Japanese)
│           └── tasks.md        # Implementation tasks (Japanese)
├── Cargo.toml           # Project dependencies
├── Cargo.lock          # Locked dependencies
└── CLAUDE.md           # This file
```

## Key Components

### Current Implementation
- **Cell enum**: Represents cell states (Covered, Uncovered(u8), Flagged, Mine)
- **Minesweeper struct**: Game state and logic
- **MinesweeperApp**: egui application wrapper
- **Fixed grid**: 9x9 with 10 mines (hardcoded)

### Dependencies
```toml
[dependencies]
rand = "0.9.0-alpha.1"
egui = "0.15"
eframe = "0.15"
```

## Development Commands

```bash
# Check for compilation errors
cargo check

# Build the project
cargo build

# Run the application
cargo run

# Run with release optimizations
cargo run --release
```

## Planned Improvements (from .kiro/specs)

### Phase 1: Fix Compilation Errors
- Fix type mismatch in match expressions
- Replace private method calls with public APIs
- Correct eframe::run_native function call

### Phase 2: Core Features
- Dynamic grid sizes with difficulty levels (Beginner/Intermediate/Expert)
- Timer and mine counter display
- Improved cell visuals and hover effects
- Question mark (?) flagging support

### Phase 3: Advanced Features
- First-click safety (never hit mine on first click)
- Pause/resume functionality
- Hint system (limited uses)
- Save/load game state
- High score tracking
- Theme support (Light/Dark)

## Technical Context

### egui/eframe Version Compatibility
The project uses egui/eframe 0.15.0, which has different APIs compared to newer versions:
- Button sizing should use `.desired_size()` or layout constraints instead of `min_size`
- UI cursor position should be accessed through `ui.max_rect()` or similar public APIs
- `eframe::run_native` has a different signature in 0.15.0

### Rust Patterns
- Uses match expressions extensively for game state
- Instant/Duration for timing
- 2D array indexing with bounds checking via cmp::max/min

### Game Logic
- Flood fill algorithm for revealing empty cells
- Adjacent mine counting for number display
- Win condition: reveal all non-mine cells
- Loss condition: reveal a mine

## Notes for AI Assistants

1. **Language Context**: Specification documents in `.kiro/specs/` are written in Japanese
2. **Version Constraints**: Must maintain compatibility with egui/eframe 0.15.0
3. **Current Priority**: Fix compilation errors before implementing new features
4. **Code Style**: Follow existing patterns for consistency
5. **Testing**: No test framework currently set up - would need to add if required

## Common Issues and Solutions

### Issue: Type mismatch in match
**Solution**: Convert all match arms to return String or use a custom display trait

### Issue: Private method access
**Solution**: Use public egui APIs or upgrade to newer egui version (requires migration)

### Issue: eframe::run_native arguments
**Solution**: Check eframe 0.15.0 documentation for correct function signature

## Build and Run Instructions

1. Ensure Rust is installed (https://rustup.rs/)
2. Clone or navigate to the project directory
3. Run `cargo build` to compile
4. Run `cargo run` to start the game

Currently the build will fail due to the compilation errors listed above. These need to be fixed first.