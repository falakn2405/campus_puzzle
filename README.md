# Class Scheduling System
 
A constraint-based, priority-driven greedy algorithm that automatically assigns university professors to rooms and time slots — built as a single Google Colab notebook with no external dependencies beyond `pandas`/`openpyxl`.

## What it does
 
Given a list of professors (with their preferred days/times, class size, and type) and a list of rooms (with capacity and day/time-restricted availability), the scheduler assigns each professor to exactly one room and time slot such that:
 
1. No two professors share the same room at the same time.
2. No professor is assigned to two classes simultaneously.
3. The assigned room has sufficient capacity for the class size.
4. The assigned room is available on the chosen day and time.
5. Professors' preferred days/times are respected — if no preferred slot is free, the professor is marked **unscheduled** with a specific reason (no silent re-assignments).

## Why a greedy algorithm
 
Professors are sorted once, by a strict three-key priority (least flexible first → external before internal → largest class first), then assigned in a single pass. This is appropriate because the priority ordering is non-negotiable, the problem needs to scale to hundreds of professors, and the goal is a correct, auditable schedule rather than a globally "optimal" one.

## Getting started
 
1. Open `class_scheduler.ipynb` in [Google Colab](https://colab.research.google.com).
2. Run each cell top-to-bottom with **Shift+Enter**.
3. When prompted (Cell 5), upload your input as an `.xlsx` file (see format below).
4. Re-run Cell 6 any time you change the input data, add a professor (Cell 9), or add a room (Cell 10).
No installation is required — only the Python standard library, `pandas`, and `openpyxl`, all of which are preinstalled in Colab.
