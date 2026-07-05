# Dicee

A simple dice rolling application built with Flutter to help beginners learn Flutter development. This project includes resources for getting started, such as the official Flutter documentation and codelab.

## Table of Contents
1. [Features](#features)
2. [How It Works](#how-it-works)
3. [Technology Stack](#technology-stack)
4. [Requirements](#requirements)
5. [Installation](#installation)
6. [Configuration](#configuration)
7. [Quick Start](#quick-start)
8. [Usage](#usage)
9. [Project Structure](#project-structure)
10. [Development](#development)
11. [Testing](#testing)
12. [Limitations](#limitations)
13. [License](#license)

## Features
### Dicee
- **What it does:** Allows users to roll virtual dice.
- **Why it exists:** To provide a simple, interactive example for Flutter beginners.
- **Why it is useful:** Helps new developers understand basic Flutter concepts like state management and UI components.

## How It Works
Dicee is a straightforward Flutter application that uses the `flutter/material.dart` package for its user interface. The core functionality involves rolling dice when a button is pressed, which updates the displayed dice image.

```dart
class DicePage extends StatefulWidget {
  @override
  _DicePageState createState() => _DicePageState();
}

class _DicePageState extends State<DicePage> {
  int leftDiceNumber = 1;
  int rightDiceNumber = 1;

  void rollDice() {
    setState(() {
      leftDiceNumber = Random().nextInt(6) + 1;
      rightDiceNumber = Random().nextInt(6) + 1;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.red,
      appBar: AppBar(
        title: Text('Dicee'),
      ),
      body: Center(
        child: Row(
          children: <Widget>[
            Expanded(
              child: Image.asset('images/dice$leftDiceNumber.png'),
            ),
            Expanded(
              child: Image.asset('images/dice$rightDiceNumber.png'),
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: rollDice,
        tooltip: 'Roll Dice',
        child: Icon(Icons.refresh),
      ),
    );
  }
}
```

## Technology Stack
| Technology | Purpose |
|------------|---------|
| Flutter | The UI software development kit created by Google. |
| Dart | The programming language used for building Flutter applications. |
| State Management | Manages the state of the application, allowing dynamic updates to the UI. |

## Requirements
- Flutter SDK (version 2.0 or higher)
- Android Studio or Xcode (for platform-specific development)

## Installation
To install and run this project, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/PartORG/Dicee_Flutter.git
   ```

2. Navigate to the project directory:
   ```sh
   cd Dicee_Flutter
   ```

3. Install dependencies:
   ```sh
   flutter pub get
   ```

4. Run the application on an emulator or physical device:
   ```sh
   flutter run
   ```

## Configuration
No additional configuration is required for this project.

## Quick Start
To quickly start using Dicee, follow these steps:

1. Clone the repository.
2. Install dependencies.
3. Run the application.

```sh
git clone https://github.com/PartORG/Dicee_Flutter.git
cd Dicee_Flutter
flutter pub get
flutter run
```

## Usage
To use Dicee, simply press the "Roll Dice" button to roll the virtual dice and see the result on the screen.

```dart
floatingActionButton: FloatingActionButton(
  onPressed: rollDice,
  tooltip: 'Roll Dice',
  child: Icon(Icons.refresh),
),
```

## Project Structure
```
Dicee_Flutter/
├── android/
│   ├── app/
│   │   └── src/
│   │       └── main/
│   │           └── kotlin/
│   │               └── com/
│   │                   └── example/
│   │                       └── dicee/
│   │                           └── MainActivity.kt
├── ios/
│   ├── Runner.xcodeproj/
│   └── Runner/
│       └── AppDelegate.swift
├── lib/
│   └── main.dart
├── test/
│   └── widget_test.dart
└── web/
    ├── index.html
    └── manifest.json
```

## Development
This project is a starting point for Flutter development. Feel free to modify and extend it as needed.

## Testing
Unit tests are included in the `test` directory.

```dart
void main() {
  test('adds one plus one', () {
    expect(1 + 1, 2);
  });
}
```

## Limitations
- This project is a simple example and does not include advanced features.
- No external dependencies are used for simplicity.

## License
This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for details.