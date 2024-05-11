# JianpuML: Jianpu Markup Language

## Overview

JianpuML is a lightweight text format for recording and sharing Jianpu, a type of numerical musical notation. It is designed to be easy to read and edit, and can be used directly in any text editor. JianpuML is particularly useful for music education, amateur music composition, and quick music score sharing.

## Design Principles

- **Simplicity**: The format is simple, making it easy for both handwritten and electronic editing.
- **Readability**: It has a clear structure that allows immediate understanding of the basic content of the music score.
- **Extensibility**: While the initial version focuses on basic functionality, the design allows for future expansions.

## Metadata

Each Jianpu file can contain several pieces of metadata that describe the basic information about the music piece:

```plaintext
Title: Song Title
Composer: Composer
Key: Key
TimeSignature: Time Signature
Tempo: Beats Per Minute
```

## Note Representation and Duration

### Note Representation

- **Basic Notes**: Numbers `1-7` directly represent the corresponding pitches.
- **Accidentals**: `#` indicates a sharp (raising the pitch by a half step), and `b` indicates a flat (lowering the pitch by a half step). For example, `6#` means raise the pitch of 6 by a half step, `3b` means lower the pitch of 3 by a half step.
- **Chords**: Multiple notes played at the same time are written together. For example, `135` represents playing 1, 3, and 5 simultaneously.

### Octave Representation

- **Higher Octave**: Adding a dot `.` after a note raises it by one octave. For example, `5.` means the 5 is played one octave higher.
- **Lower Octave**: Adding a dot `.` before a note lowers it by one octave. For example, `.5` means the 5 is played one octave lower.

### Duration Representation

- A slash `/` followed by a number can be added after each note to indicate its duration, where the number represents the note's value as a fraction of a whole note. For example, `5/4` means 5 is a quarter note, `6#/8` means a sharp 6 is an eighth note.

## Example

The following example shows how to use the JianpuML format, including representations of notes' octaves and durations:

```plaintext
Title: Twinkle Twinkle Little Star Variations
Composer: Traditional
Key: C major
TimeSignature: 4/4
Tempo: 100

1/4 1/4 5./4 5./4 | 6./4 6./4 5./2 |
4/4 4/4 3/4 3/4 | 2/4 2/4 1/2 |
```
