# DawAI Playlist Functions And Goals

## Goal
Build a DawAI Playlist modeled after FL Studio Playlist behavior, with the same essential arrangement workflow and clip-edit capabilities for WAV/MP3 audio and pattern/automation style timeline composition.

## Core Functional Outline

### 1) Arrangements
- Multiple arrangements in one project (Arrangement 1, Arrangement 2, Radio Edit, Live Edit).
- Each arrangement stores a separate timeline structure.
- Shared project resources remain reusable across arrangements.

### 2) Playlist Tracks (Timeline Lanes)
- Horizontal lanes used as clip containers.
- Playlist tracks are timeline containers, separate from mixer routing inserts.
- Optional track mode:
  - Free
  - Audio
  - Instrument
  - Automation
- Track controls:
  - name
  - color
  - mute/solo style lane auditioning
  - lane height control

### 3) Clip Types
- Pattern clips (pattern references for instrument triggering).
- Audio clips (wav/mp3 and other supported formats).
- Automation clips (envelope curves for parameters).
- Markers/events for structure and navigation.

### 4) Timeline Top Controls
- Time ruler with bars/beats and optional time display.
- Playhead placement by click.
- Loop region creation by drag.
- Snap modes (magnet behavior):
  - None
  - Step
  - Beat
  - Bar
  - Additional context modes later (line/cell/event-like).
- Horizontal and vertical zoom controls.
- Song vs Pattern playback behavior compatibility at transport level.

### 5) Playlist Editing Tools
- Select tool.
- Draw tool.
- Paint/repeat placement workflow.
- Slice tool (split clips at cursor).
- Slip tool (move source content inside fixed clip region).
- Mute tool (non-destructive arrangement audition).
- Delete tool.
- Zoom tool.

### 6) Audio Clip Editing Requirements
- Move clip in time/lane.
- Resize left/right edges.
- Stretch/time-stretch with rate control.
- Pitch shift per clip (semitones/fine).
- Resample mode toggle (pitch follows rate behavior).
- Slip editing (offset source playback window inside clip bounds).
- Slice into independent pieces.
- Fade in/fade out and crossfade support (phase 2).
- Reverse/consolidate/render operations (phase 2).

### 7) Pattern Clip Behavior Requirements
- Pattern clips reference shared pattern data.
- Repeat/loop-friendly placement.
- Unique clone workflow (make unique style behavior).
- Pattern clip length/loop behavior options.

### 8) Automation Clip Behavior Requirements
- Point-based envelope editing.
- Curve/tension/shape options.
- Link to mixer/plugin/instrument parameters.
- Reuse/copy/split/clone automation regions.

### 9) Structural/Advanced Arrangement Features
- Time markers for section labels (Intro, Build, Drop, Verse, etc).
- Clip grouping and move-as-block workflow.
- Track grouping and visibility management.
- Clip/track locking to prevent accidental edits.
- Take-lane style audio recording organization and comp workflow.
- Performance mode alignment (future live triggering workflow).

## Immediate Implementation Goals (Current Sprint)
- Implement a dedicated `PlaylistView` widget as the main timeline editor.
- Integrate arrangement selector and clip editing controls in `MainWindow`.
- Implement essential audio-clip operations now:
  - place
  - move
  - resize
  - stretch
  - pitch
  - resample mode
  - slice
  - slip
- Keep GUI responsive during timeline interaction.
- Preserve existing AIFRED integration and loaded-track analysis context.

## Acceptance Criteria For "Essential FL-Style Playlist"
- User can load a WAV/MP3 and place it as a playlist clip.
- User can drag the clip across lanes/time with snap behavior.
- User can slice the clip and edit pieces independently.
- User can stretch clip length and adjust per-clip pitch.
- User can toggle resample-like playback mode per clip.
- User can create/use multiple arrangements and switch between them.
- Playback and playhead remain responsive during edits.

## Not In Scope For This Immediate Pass
- Full DAWproject import/export mapping.
- Full crossfade/fade-shape editor parity.
- Full comp lane and take manager UI parity.
- Performance mode launcher grid parity.
- Deep mixer-routing automation matrix parity.

These are queued for follow-up phases after essential playlist editing is stable.
