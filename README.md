# Tetris (project for compsci 2)

A simple TUI implementation of Tetris made in Python.

## Planned features

- barebones Tetris

- per-game stat tracking and saving them to a database (SQLite)

  - stat viewer

- JSON configuration file for setting simple settings (controls, ghost block)

## UML chart (WIP)

```plantuml
hide circle
class UIElement as "**UIElement**"
class Game as "**Game**" {
    paused
    pause()
}
class PauseMenu as "**PauseMenu**" {
    position
}
class Hold as "**Hold**" {
    position
    tetromino
}
class Playfield as "**Playfield**" {
    position
    lines
    has_tetris()
    clear_line()
    clear()
}
class Stats as "**Stats**" {
    position
    score
    lines
    time
}
class Queue as "**Queue**" {
    position
    queue
    bag
    get_bag()
    update_queue()
}
class Tetromino as "**Tetromino**" {
    position
    rotation
    hard_drop()
    soft_drop()
    rotate()
}
class IShape as "**IShape**" {
    shape
    color
}
class JShape as "**JShape**" {
    shape
    color
}
class LShape as "**LShape**" {
    shape
    color
}
class OShape as "**OShape**" {
    shape
    color
}
class SShape as "**SShape**" {
    shape
    color
}
class ZShape as "**ZShape**" {
    shape
    color
}
class TShape as "**TShape**" {
    shape
    color
}

class TShape extends Tetromino
class ZShape extends Tetromino
class SShape extends Tetromino
class OShape extends Tetromino
class LShape extends Tetromino
class JShape extends Tetromino
class IShape extends Tetromino

class Game extends UIElement
class Stats extends UIElement
class Playfield extends Game
class Queue extends Game
class PauseMenu extends Game
class Hold extends Game
Playfield o-- Tetromino
Queue o-- Tetromino
Stats <-- Tetromino
Stats <-- Playfield
Hold <-- Playfield
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
