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
Arranger: Arranger

Key: Key Signature
TimeSignature: Time Signature
Tempo: Beats Per Minute
DefaultDuration: Default note value (e.g., 4 for a quarter note)
Staff: Set to true when using JianpuML to directly express staff notation.
```

Notably, the following fields can be modified multiple times throughout the score to accommodate different sections of the music:
- Key
- TimeSignature
- Tempo
- DefaultDuration

## Note Representation and Duration

### Note Representation

- **Basic Notes**: Numbers `1-7` directly represent the corresponding pitches.
- **Accidentals**: `#` for a sharp, `b` for a flat. For example, `6#` represents a sharp 6, `3b` represents a flat 3.
- **Chords**: Multiple notes played simultaneously are joined by commas, e.g., `1,5` means playing 1 and 5 together.
- **Legato**: Notes enclosed in parentheses () are played legato (smoothly connected). For example, (3 5 6) represents three notes played in legato.
- **Fixed Pitch Notation**: In addition to supporting the numerical representation, this system also supports fixed pitch letter notation using CDEFGAB to represent absolute pitches. Thus, JianpuML can express not only Jianpu but also directly represent staff notation.

### Octave Representation

- **Higher Octave**: A dot `.` after a note indicates it is one octave higher, e.g., `5.` means the note 5 is played an octave higher.
- **Lower Octave**: A dot `.` before a note indicates it is one octave lower, e.g., `.5` means the note 5 is played an octave lower.

### Duration Representation

- Each note or group of notes may follow a slash `/` and a number or letter indicating the duration.
  - **Numbers**: The number represents the type of note. For example, `5/4` indicates a quarter note.
  - **Letters**: For easier input, you can also use letters to represent shorter note durations:
    - `a` represents a sixteenth note (e.g., `5/a`).
    - `b` represents a thirty-second note (e.g., `5/b`).
    - `c` represents a sixty-fourth note (e.g., `5/c`).
- **Default Duration**: The DefaultDuration can be set to represent the most commonly used note duration (e.g., 4 for quarter notes). If a note's duration matches the default duration, its value can be omitted. Additionally, DefaultDuration can be modified multiple times throughout the score, allowing for more efficient input as different sections of the music may require different default note durations. 
- **Dotted Notes**: Use a dot `.` to extend the duration by half. For example, `5/4.` indicates a dotted quarter note, and `5/a.` indicates a dotted sixteenth note.
- **Triplets**: Notes enclosed in square brackets [] represent a triplet. For example, [1 3 5] represents a triplet.


## Example

The following example illustrates the use of the JianpuML format, including representations of note octaves and durations, as well as part separation:

```
Title: Twinkle Twinkle Variation
Composer: Composer
Arranger: Arranger

Key: D major
TimeSignature: 4/4
Tempo: 100
DefaultDuration: 4

1 1 5 5 | 6 6 5/2 | 4 4 3 3 | 2 2 1/2 |
1,5 1,5 4 4 | 3 3 2/2 | 1,5 1,5 4 4 | 3 3 2/2 |

DefaultDuration: 8
1 1 1 1 5 5 5 5 | 6 6 6 6 5/2 ｜[ 4 4 4 ] [ 3 3 3 ] | ( 2 2 ) 1/2 |
```

The following example demonstrates using JianpuML to directly express staff notation:


```
Title: 北京的金山上
Composer: 藏族民歌
Arranger: 单简

Key: F
Staff: true
TimeSignature: 4/4
Tempo: 108
DefaultDuration: 8

A/4 A C. E./4 E. D. | C./4 (D. E.) D./4 (D./a C./a C./a A/a) | (A/2. C./4) | E./4 D. (C./a A/a) C./4 D. E.|
A/4 C. D. (A/4 A/A G/A G/A E/A) | E/1 | A A G E A A G E | A A/A A/A C. E. E. (C./A D./A) (D./A C./A C./A A/A) |
A/2 C. (A/A C./A) D. E. | A (A/A G/A E/4) E G A C. | D. D./A D./A (D./A C./A) (C./A A/A) (A/2 | A/4) (d./a c./a c./a a/a) a a a 0
```
