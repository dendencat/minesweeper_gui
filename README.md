# Minesweeper GUI

A Minesweeper game implemented in Rust with a graphical user interface using the egui/eframe framework.

## Features

- Classic Minesweeper gameplay
- Multiple difficulty levels (Beginner, Intermediate, Expert, Custom)
- Timer and mine counter
- Flag and question mark placement
- First-click safety guarantee
- Game pause/resume functionality
- Hint system
- High score tracking
- Game save/load functionality
- Theme settings (Light/Dark)

## Screenshots

*(Screenshots will be added after implementation)*

## Requirements

- Rust 1.56.0 or higher
- Cargo (Rust package manager)

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/minesweeper_gui.git
cd minesweeper_gui

# Build and run
cargo run --release
```

## Usage

### Starting a Game

1. Launch the application
2. Select a difficulty level from the main menu
3. Click "New Game" to start playing

### Gameplay

- **Left Click**: Reveal a cell
- **Right Click**: Cycle between flag, question mark, and covered states
- **Reset Button**: Start a new game
- **Pause Button**: Pause/resume the game
- **Hint Button**: Reveal one safe cell (limited uses)

## Development

### Dependencies

- [rand](https://crates.io/crates/rand) - Random number generation
- [egui](https://crates.io/crates/egui) - GUI framework
- [eframe](https://crates.io/crates/eframe) - egui wrapper

### Building

```bash
# Debug build
cargo build

# Release build
cargo build --release
```

### Testing

```bash
# Run all tests
cargo test

# Run a specific test
cargo test test_mine_placement
```

## Improvement Plan

This project is currently undergoing improvements. The main areas of focus are:

1. Fixing compilation errors
2. Refactoring the basic structure
3. Improving UI/UX
4. Implementing a menu system
5. Adding additional features
6. Implementing persistence functionality
7. Testing and debugging

For detailed improvement plans, see the documents in the `.kiro/specs/minesweeper-improvement/` directory.

## License

Apache License 2.0

## Contributing

Contributions are welcome! Feel free to report bugs, request features, or submit pull requests.

## Author

dendencat