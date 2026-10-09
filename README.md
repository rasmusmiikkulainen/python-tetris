# Tetris in Python

A simple TUI implementation of Tetris made in Python.

## Planned features

- barebones Tetris

- per-game stat tracking and saving them to a database (SQLite)

  - stat viewer

- JSON configuration file for setting simple settings (controls, ghost block)

## UML chart (WIP)

```mermaid
classDiagram
    class UIElement{
        fps
    }
    class MainMenu{
        play()
        view_stats()
    }
    class StatsViewer{
        pb_time
        pb_time_date
        pb_score
        pb_score_date
        get_stats()
    }
    class Hold{
        tetromino
        release_tetromino()
    }
    class Config{
        ghost_block
        rotate_bind
        soft_drop_bind
        hard_drop_bind
        hold_bind
        left_bind
        right_bind
        parse()
        create_default()
    }
    class Playfield{
        gravity
        active_tetromino
        lines
        hard_drop()
        soft_drop()
        ghost_block()
        rotate_tetromino()
        hold_tetromino()
        has_tetris()
        clear_line()
        clear()
        game_over()
    }
    class Stats{
        date
        level
        score
        lines
        gametime
        save()
    }
    class Queue{
        queue
        bag
        get_bag()
        update_queue()
    }
    class Tetromino{
        list
        position
    }
    class IShape{
        shape
        color
    }
    class JShape{
        shape
        color
    }
    class LShape{
        shape
        color
    }
    class OShape{
        shape
        color
    }
    class SShape{
        shape
        color
    }
    class ZShape{
        shape
        color
    }
    class TShape{
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
    UIElement <|-- Stats
    UIElement <|-- Playfield
    UIElement <|-- Queue
    UIElement <|-- Hold
    UIElement <|-- StatsViewer
    UIElement <|-- MainMenu
    Playfield o-- Tetromino: has
    Queue o-- Tetromino: has
    StatsViewer o-- Stats: has
    Playfield <-- Stats : depends on
    Hold <-- Playfield : uses
    Stats <-- Playfield : depends on
    Config <-- Playfield
    Tetromino <-- Playfield
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
