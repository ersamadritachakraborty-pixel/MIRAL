# MIRAL
A minimalist, dark-mode Jetpack Compose Android app for unsent thoughts, time-locked capsules, and drifting night-sky echoes.
> *A quiet corner of Android for words you never sent, and memories waiting for their moment.*

**MIRAL** is an editorial, dark-mode native Android application built in **100% Kotlin and Jetpack Compose**. Designed around calm visual restraint rather than social noise, MIRAL turns private reflection into a tactile experience—allowing users to either lock a thought inside a time-blurred capsule or dissolve it into an interactive night sky.

---

## Why I Built MIRAL

Most mobile apps are engineered to demand attention—through notifications, streaks, and public feeds. As a Computer Science student exploring modern Android architecture and motion-driven UI design, I wanted to build the exact opposite: software that feels deliberate, atmospheric, and emotionally grounded.

MIRAL started with a simple design challenge: **Can a single-screen Compose canvas feel as tactile as writing on paper late at night?** Every visual decision—from the midnight gradient (`#07090F` to `#111827`) and warm starlight gold accents (`#E8C882`) to the serif typography and particle physics—was crafted to make an unsent thought feel meaningful.

---

## Core Experience & Features

| Feature | Experience | Technical Implementation |
| :--- | :--- | :--- |
| **Ambient Midnight Canvas** | A serene, twinkling night-sky backdrop that sets an unhurried tone the moment the app opens. | Custom Jetpack Compose `Canvas` driven by `rememberInfiniteTransition` phase-shifted sine waves. |
| **Release to Sky (`SkyEchoView.kt`)** | Typing a thought and tapping **Release ✦** dissolves the words into rising golden particles and adds the note to an anonymous sky archive. | `Animatable` physics loop rendering 80 directional particles with alpha decay and dynamic state updates. |
| **Sealed Time Vault (`VaultView.kt`)** | Locking a note seals it behind a frosted-glass card with a live ticking countdown, keeping the message blurred until the timer reaches zero. | Real-time coroutine ticker (`1000ms` interval) paired with Compose `Modifier.blur` and `Locale`-safe formatting. |
| **Editorial Glassmorphism** | Translucent surfaces, hairline borders, and high-contrast serif prompts that prioritize readability and calm focus. | Custom Material 3 color tokens, `RoundedCornerShape` clipping, and layered alpha overlays. |

---

## Architecture & Tech Stack

MIRAL follows a clean, modular composable structure with zero third-party UI bloat—relying strictly on modern Android Jetpack APIs for reliability, smooth 60/120fps rendering, and fast build times.

- **Language:** Kotlin
- **UI Toolkit:** Jetpack Compose (Material 3)
- **Graphics & Motion:** Compose `Canvas`, `Animatable`, `FastOutSlowInEasing`, `Modifier.blur`
- **Concurrency:** Kotlin Coroutines (`LaunchedEffect` lifecycle-aware timers)
- **SDK Configuration:** `compileSdk = 37`, `targetSdk = 37`, `minSdk = 24`

### Project Layout

```text
app/src/main/java/com/example/miral/
├── MainActivity.kt   # Starfield canvas, composer card, particle burst engine & sheet orchestration
├── VaultView.kt      # Time-capsule model, live countdown ticker & blurred unlock state
└── SkyEchoView.kt    # Anonymous night-sky echoes reader with cyclic navigation
