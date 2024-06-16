# JianpuML: Jianpu Markup Language

## Overview

JianpuML is a minimalist markup language for numbered musical notation. JianpuML focuses on recording the pitch and duration of notes, intentionally omitting other musical elements such as dynamics, ornaments, and repeat signs. The primary goal of JianpuML is to facilitate the conversion of Jianpu into formats that are easily readable and usable by standard music notation software.

## Design Principles

- **Simplicity**: The format is simple, easy to handwrite and edit electronically.
- **Readability**: The structure is clear, allowing one to understand the basic content of the music at a glance.

## Metadata

Each JianpuML file can include several metadata fields describing the basic information of the piece:

```
Title: Song Title
Composer: Composer
Key: Key Signature
TimeSignature: Time Signature
Tempo: Beats Per Minute
DefaultDuration: Default note value (e.g., 4 for a quarter note)
```

## Note Representation and Duration

### Note Representation

- **Basic Notes**: Numbers `1-7` directly represent the corresponding pitches.
- **Accidentals**: `#` for a sharp, `b` for a flat. For example, `6#` represents a sharp 6, `3b` represents a flat 3.
- **Chords**: Multiple notes played simultaneously are joined by commas, e.g., `1,5` means playing 1 and 5 together.

### Octave Representation

- **Higher Octave**: A dot `.` after a note indicates it is one octave higher, e.g., `5.` means the note 5 is played an octave higher.
- **Lower Octave**: A dot `.` before a note indicates it is one octave lower, e.g., `.5` means the note 5 is played an octave lower.

### Duration Representation

- Each note or group of notes may follow a slash `/` and a number indicating the duration. The number represents the type of note, such as `5/4` for a quarter note. If a note's duration matches the default duration, its value can be omitted.
- **Dotted Notes**: Use a dot `.` to extend the duration by half. For example, `5/4.` indicates a dotted quarter note.

## Example

The following example illustrates the use of the JianpuML format, including representations of note octaves and durations, as well as part separation:

```
Title: Twinkle Twinkle Variation
Composer: Traditional
Key: D major
TimeSignature: 4/4
Tempo: 100
DefaultDuration: 4

1 1 5 5 | 6 6 5/2 |
4 4 3 3 | 2 2 1/2 |
1,5 1,5 4 4 | 3 3 2/2 |
5 5 4 4 & .5 .5 .4 .4 | 3 3 2/2 |
```

