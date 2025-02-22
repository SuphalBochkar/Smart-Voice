# Smart Voice Assistant for Professionals

A mobile application prototype that captures voice conversations during meetings, transcribes them, and converts them into structured digital actions. Designed for busy professionals, this tool helps you quickly identify tasks, calendar events, and key discussion points—all while you focus on the conversation.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Implementation Plan](#implementation-plan)
- [Project Structure](#project-structure)

---

## Overview

In today's fast-paced professional environment, missing out on key action items during meetings can be a significant setback. This project addresses that challenge by providing a straightforward mobile solution that:

- **Records** voice conversations.
- **Transcribes** the recorded audio in real-time.
- **Extracts** actionable items like tasks, meeting details, and key discussion points.
- **Displays** all information in a clean, user-friendly interface.

This approach stays true to tried-and-true methods while leveraging modern technology to enhance efficiency.

---

## Features

- **Voice Processing:**

  - Record meetings and transcribe conversations with support for English, including basic accent variations.

- **Action Extraction:**

  - Identify and extract key action items, such as tasks, dates, times, and discussion highlights.

- **Action Generation:**

  - Automatically create digital actions:
    - Calendar events
    - To-do items with deadlines
    - Meeting summaries
    - Options to share key points via email or messaging

- **User Interface:**
  - Real-time display of transcribed text.
  - Simple, intuitive mobile UI with editing capabilities.
  - Visual indicators to show processing status during recording and transcription.

---

## Tech Stack

- **Mobile Framework:**

  - **React Native with Expo (Managed Workflow):** Enables fast, cross‑platform development with minimal native configuration.

- **Audio Recording:**

  - **expo-av:** For capturing voice conversations within the Expo environment.

- **Speech-to-Text:**

  - **Google Cloud Speech-to-Text API:** Converts recorded audio to text.
  - _Alternative:_ **react-native-voice** if an all‑in‑one solution is preferred.

- **Action Extraction:**

  - **TypeScript & Regex:** Implements straightforward logic to parse transcribed text and extract actionable items.

- **User Interface:**

  - **React Native Components:** For building a clean, functional UI.
  - **Nativewind/Tailwind CSS:** For rapid, consistent styling.

- **Backend (Optional):**

  - **Node.js/Express:** For offloading processing tasks and integrating additional API calls if needed.

- **Additional Tools:**
  - **Axios:** For HTTP requests to external APIs.
  - **Expo Permissions:** To manage microphone and audio recording access.

---

## Implementation Plan

1. **Project Setup**

   - Initialize a new React Native project using Expo.
   - Configure necessary permissions (microphone and audio recording) using Expo Permissions.

2. **Audio Recording & Transcription**

   - Integrate `expo-av` to record voice conversations.
   - Implement functionality to send recorded audio to the Speech-to-Text API for transcription.

3. **Real-time Transcription Display**

   - Present the transcribed text on the app interface in real-time.

4. **Action Extraction**

   - Develop TypeScript logic (using regex or similar methods) to extract:
     - Action items/tasks
     - Meeting details (date and time)
     - Key discussion points

5. **Action Generation**

   - Map extracted data into digital actions:
     - Create calendar events.
     - Generate to-do items with deadlines.
     - Produce meeting summary notes.
     - Provide sharing options (email/messaging) for key points.

6. **User Interface Development**
   - Build the UI with standard React Native components.
   - Ensure real-time updates and editing capabilities for transcribed text and extracted actions.
   - Include visual cues for processing status during recording, transcription, and action generation.

---

## Project Structure

```plaintext
smart/
├── app/                   # Expo Router: screens and navigation layouts
│   ├── (tabs)/           # Grouping for tab-based navigation
│   │   ├── index.tsx     # Main tab screen
│   │   └── _layout.tsx   # Layout specific to tabs (e.g., tab navigator)
│   ├── +not-found.tsx     # 404 screen for unmatched routes
│   └── _layout.tsx       # Global layout for all screens/routes
├── assets/               # Static assets (images, fonts, etc.)
│   ├── fonts/
│   └── images/
├── components/           # Reusable UI components
│   ├── ui/              # Presentation-level components (buttons, icons, etc.)
│   ├── common/          # Shared layout components
│   └── tests/           # Component tests (if needed)
├── hooks/                # Custom React hooks (e.g., useColorScheme, useThemeColor)
├── services/             # Business logic and API services
│   ├── AudioService.ts  # Audio recording/processing logic
│   ├── TranscriptionService.ts # Integration with Speech-to-Text API
│   └── ActionExtractor.ts # Logic to extract actions/tasks from text
├── constants/            # Shared constants (colors, styles, etc.)
│   └── Colors.ts
├── utils/                # Helper functions and utilities (formatting, data parsing)
├── scripts/              # Utility scripts (e.g., project reset, build tasks)
│   └── reset-project.js
├── types/                # (Optional) Custom TypeScript types and interfaces
├── config/               # (Optional) Configuration files and API keys management
├── package.json          # Project metadata and dependencies
├── tsconfig.json         # TypeScript configuration
├── app.json              # Expo configuration
├── README.md             # Project overview and instructions
└── .gitignore            # Files and folders to ignore in Git
```
