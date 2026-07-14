# Element Alchemy

A single-view Android app for the Projects Collection brief's "creative calculator that doesn't calculate numbers."

## Concept
Element Alchemy borrows the *look and interaction pattern* of a calculator — a keypad grid feeding a display — but replaces arithmetic with an invented system of elemental fusion. Six primal elements (Fire, Water, Earth, Air, Light, Shadow) can be combined two at a time. Each of the 21 possible combinations resolves to an original, hand-authored result (name + one-line description + emoji), e.g. Fire + Shadow = **Ember**, "a flame that refuses to die in the dark."

This is the app's Unique Selling Point: the calculator metaphor is repurposed for a poetic/lexical output instead of a numeric one.

## Required elements from the brief
- **Single-view app**: everything happens in `MainActivity` / `activity_main.xml`.
- **Creative, non-numeric calculator**: the element grid + display, see `Fusions` table in `MainActivity.kt`.
- **Informative pop-up (modal) view**: tap the ⓘ icon top-right to open `InfoDialogFragment`, a true `DialogFragment`, not a system alert.
- **Custom launch screen**: `Theme.ElementAlchemy.Splash` + `ic_launch_symbol.xml` (an original alchemy sigil), wired up with `androidx.core.splashscreen`.
- **Custom app icon**: adaptive icon built from `ic_launcher_background.xml` / `ic_launcher_foreground.xml` (same sigil motif).

## How to open
1. Open Android Studio (Koala/Ladybug or newer recommended).
2. `File > Open` and select this project's root folder (the one containing `settings.gradle.kts`).
3. Let Gradle sync (requires network access the first time, to download Gradle 8.6 and the AGP/Kotlin plugins).
4. Run on an emulator or device with **API 26+**.

## Project structure
```
app/src/main/java/com/example/elementalchemy/
  MainActivity.kt          – UI wiring, fusion state machine
  InfoDialogFragment.kt    – the modal info view
app/src/main/res/
  layout/activity_main.xml – the single view
  layout/dialog_info.xml   – the modal's layout
  drawable/ic_launch_symbol.xml, ic_launcher_*.xml – custom art
  values/                  – strings, colors, themes (incl. splash theme)
```
