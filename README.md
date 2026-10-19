# Modus — Native iOS Calendar & On-Device AI

A personal iOS application exploring private calendar storage, customizable scheduling views, home-screen widgets, and a locally running voice assistant.

**Status:** Active development · **Developer:** Jackson Shults · **Source:** Private; access available on request for technical review.

## What I built

- A SwiftUI calendar interface with a month grid, selected-day events, a monthly agenda, and customizable home modules.
- SwiftData models for events and named, color-coded calendars.
- Event editing with notes, locations, all-day settings, recurrence options, and local notification reminders.
- WidgetKit integration using shared App Group snapshots for calendar widgets.
- A voice assistant using on-device speech recognition and MLX inference with Qwen2.5-0.5B-Instruct.

## Technical approach

| Component | Technology and design |
| --- | --- |
| User interface | SwiftUI; AppStorage for persistent preferences |
| Data | SwiftData for local event and calendar persistence |
| Widgets | WidgetKit timelines, App Groups, serialized snapshots |
| Notifications | UserNotifications scheduling and permission handling |
| AI | MLX Swift LM, Hugging Face model loading, durable model caching |
| Speech | Apple Speech with on-device recognition required; AVFAudio capture |

## Design decisions

**Local persistence:** Calendar data stays in a local SwiftData store. Widget updates use a separate shared snapshot suited to the extension.

**On-device inference:** The app downloads model weights during setup, then runs language-model inference locally. Speech capture rejects recognition paths that lack on-device support.

**Explicit assistant boundaries:** The voice assistant answers calendar questions. Event creation, changes, and deletion remain in the calendar interface; the assistant is instructed not to claim it performed edits.

## Current limits and validation

This is a development project. Voice editing and calendar-provider synchronization are not implemented. Generated answers may be inaccurate, and speech support varies by device and language. No automated test target is currently included. A build was not verified during repository preparation because Xcode cache access was restricted.

## Technical review

The application source is kept in a private repository. For hiring-related code review, contact me through my GitHub profile: [jacksonlshults](https://github.com/jacksonlshults).

This public showcase contains a project overview, without application source code or model weights.
