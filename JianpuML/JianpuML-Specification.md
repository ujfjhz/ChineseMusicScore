# JianpuML: Jianpu Markup Language

## Overview

JianpuML is a minimalist Jianpu markup language. It focuses exclusively on documenting the pitch and duration of notes, intentionally omitting other musical elements such as dynamics, ornaments, and repeat signs. The primary goal of JianpuML is not to serve as a comprehensive tool for expressing the complexity of Jianpu, but rather to expedite the conversion of Jianpu into a format that can be easily interpreted and utilized in standard music notation software.

## Design Principles

- **Simplicity**: The format is simple, making it easy for both handwritten and electronic editing.
- **Readability**: It has a clear structure that allows immediate understanding of the basic content of the music score.

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
Key: D major
TimeSignature: 4/4
Tempo: 100

1/4 1/4 5/4 5/4 | 6/4 6/4 5/2 |
4/4 4/4 3/4 3/4 | 2/4 2/4 1/2 |
5/4 5/4 4/4 4/4 | 3/4 3/4 2/2 |
5/4 5/4 4/4 4/4 | 3/4 3/4 2/2 |

```
