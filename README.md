# PyConsole

A lightweight console‑formatting toolkit designed to create clean, readable, and visually structured terminal output. PyConsole provides headers, subheaders, breakers, numbered lists, and plain lists — all using a consistent visual language that makes CLI tools easier to read and debug.

## Overview

PyConsole focuses on one thing: making console output look good without adding complexity. It gives developers a simple, modular set of formatting utilities that can be reused across any CLI project, debugging tool, or text‑based engine.

This makes PyConsole ideal for:

- CLI applications

- Debugging utilities

- Text‑based engines and menus

- Inventory or data viewers

- Teaching tools

- Logging and inspection tools

Its output is structured, readable, and visually distinct, helping developers quickly understand the information being displayed.

## Why PyConsole?

Most console output ends up messy — inconsistent spacing, unclear sections, and walls of text. PyConsole solves this by giving you a consistent formatting system:

- Headers for major sections

- Subheaders for entries or subsections

- Numbered or plain lists for fields

- Breakers to visually separate content

Instead of manually writing print statements or repeating formatting logic, PyConsole centralizes everything into a clean, reusable API.

## Core Features

- Clean, Consistent Headers

- Create visually distinct section headers that stand out in the console.

### Subheaders for Entries

- Perfect for labeling items, records, or subsections.

### Numbered and Plain Lists

- Display structured data in a readable, predictable format.

### Visual Breakers

- Use empty subheaders or separators to break up content and improve readability.

## Minimal, Modular Design

PyConsole is intentionally small and dependency‑free.It focuses on formatting — nothing more, nothing less.

Example Output
```txt
||=====[Items]=====||

[---[Potion]---]

1 - Name: Potion
2 - Heals: 25
3 - Type: Consumable

[---[==]---]
```
## Class Structure
```python
class PyConsole:

    @staticmethod
    def PrintHeader(title):
        return f"||=====[{title}]=====||\n"

    @staticmethod
    def PrintSubHeader(title):
        return f"[---[{title}]---]\n"

    @staticmethod
    def PrintNumberedList(data):
        output = ""
        for i, (key, value) in enumerate(data.items(), start=1):
            output += f"{i} - {key}: {value}\n"
        return output

    @staticmethod
    def PrintList(data):
        output = ""
        for key, value in data.items():
            output += f"{key}: {value}\n"
        return output
```
## Usage Example
```python
from PyConsole import PyConsole

print(PyConsole.PrintHeader("Items"))
print(PyConsole.PrintSubHeader("Potion"))

fields = {
    "Name": "Potion",
    "Heals": 25,
    "Type": "Consumable"
}

print(PyConsole.PrintNumberedList(fields))
print(PyConsole.PrintSubHeader("=="))
```
This produces clean, structured console output with minimal effort.

## Summary

PyConsole provides a simple, reusable formatting system for clean terminal output. Its headers, subheaders, lists, and breakers make it easy to build readable CLI tools, debugging utilities, and text‑based engines — all while keeping your code clean and consistent.

Requires: Python 3.x
