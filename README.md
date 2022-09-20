# multipick

[![image](https://github.com/anafvana/multipick/actions/workflows/ci.yml/badge.svg)](https://github.com/anafvana/multipick/actions/workflows/ci.yml)
[![PyPI](https://img.shields.io/pypi/v/multipick.svg)](https://pypi.org/project/multipick/)
[![PyPI](https://img.shields.io/pypi/dm/multipick)](https://pypi.org/project/multipick/)

**multipick** is a small python library based on [wong2's pick](https://github.com/wong2/pick) which allows you to create a curses-based interactive selection in the terminal. With **multipick** you can asign options to groups.

![](example/basic.gif)

## Installation

    $ pip install multipick

## Usage

**multipick** comes with a simple api:

    >>> from multipick import multipick

    >>> instructions = "Assign languages to groups 'a', 'b' or '1'."
    >>> options = ["Java", "JavaScript", "Python", "PHP", "C++", "Erlang", "Haskell"]
    >>> groups:set = {"a", "b", 1}
    >>> selected = multipick(options, groups, instructions, indicator="=>", default_index=2)
    >>> print(f"Here is your assignment: {selected}")

**output**:

    >>> {'1': [], 'a': [("JavaScript", 1)], 'b': []}

## Options

- `options`: a list of options to choose from
- `groups`: a list of ints and/or characters symbolising groups (max-length per item is 1)
- `instructions`: (optional) a title above options list
- `indicator`: (optional) custom the selection indicator, defaults to `*`
- `default_index`: (optional) index of item where cursor starts at by default
- `handle_all`: (optional) define whether it is mandatory to assign all options to groups, defaults to `False`

## Community Projects

[wong2's pick](https://github.com/wong2/pick): Original pick project, for selecting one or more options (no grouping)

[pickpack](https://github.com/anafvana/pickpack): A fork of `multipick` to select tree data.
