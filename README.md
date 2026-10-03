# Tetris (project for compsci 2)

A simple TUI implementation of Tetris made in Python.

## Planned features

- barebones Tetris

- per-game stat tracking and saving them to a database (SQLite)

  - stat viewer

- JSON configuration file for setting simple settings (controls, ghost block)

## UML chart (WIP)

```mermaid
classDiagram
    class UIElement

class Game {
    paused
    pause()
}

class PauseMenu {
    position
}

class Hold {
    position
    tetromino
}

class Playfield {
    position
    lines
    has_tetris()
    clear_line()
    clear()
}

class Stats {
    position
    score
    lines
    time
}

class Queue {
    position
    queue
    bag
    get_bag()
    update_queue()
}

class Tetromino {
    position
    rotation
    hard_drop()
    soft_drop()
    rotate()
}

class IShape {
    shape
    color
}

class JShape {
    shape
    color
}

class LShape {
    shape
    color
}

class OShape {
    shape
    color
}

class SShape {
    shape
    color
}

class ZShape {
    shape
    color
}

class TShape {
    shape
    color
}

Tetromino <|-- TShape
Tetromino <|-- ZShape
Tetromino <|-- SShape
Tetromino <|-- OShape
Tetromino <|-- LShape
Tetromino <|-- JShape
Tetromino <|-- IShape

UIElement <|-- Game
UIElement <|-- Stats
Game <|-- Playfield
Game <|-- Queue
Game <|-- PauseMenu
Game <|-- Hold

Playfield o-- Tetromino
Queue o-- Tetromino
Tetromino --> Stats
Playfield --> Stats
Playfield --> Hold
```

## Expected external dependencies:

- Windows:

  - [windows-curses](https://pypi.org/project/windows-curses/)

- Linux:

  - none

## Resources

- [Tetris Guideline](https://tetris.wiki/Tetris_Guideline)

- [curses howto](https://docs.python.org/3/howto/curses.html)

- https://en.wikipedia.org/wiki/Box-drawing_characters
