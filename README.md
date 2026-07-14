# Mood Journal

A multiple-view Android app for the Projects Collection brief, with basic storage of user preferences.

## Concept
Mood Journal treats feelings like passing weather rather than fixed labels. Three tabs:
- **Log** — tap one of eight moods, add an optional one-line note, save it.
- **History** — a scrollable, timestamped record of everything you've logged (newest first).
- **Settings** — set a display name, pick an accent colour, and toggle a daily reminder preference. These are the app's **stored user preferences**, persisted with `SharedPreferences` so they survive app restarts.

The Unique Selling Point is the low-pressure framing (no scores, streaks or gamification — see the `data-analysis`-free `MoodRepository`) combined with a genuinely persistent, personalised settings layer rather than a cosmetic one.

## Required elements from the brief
- **Multiple-view app**: `MainActivity` hosts three fragments (`LogFragment`, `HistoryFragment`, `SettingsFragment`) switched via a `BottomNavigationView`.
- **Storage of basic preferences**: `SettingsFragment` + `MoodRepository` — display name, accent colour key, and reminder toggle are written to and read from `SharedPreferences`.
- **Informative pop-up (modal) view**: the ⓘ icon in the toolbar opens `InfoDialogFragment`, a true `DialogFragment`.
- **Custom launch screen**: `Theme.MoodJournal.Splash` + `ic_launch_symbol.xml` (an original "mood-wave journal" mark), via `androidx.core.splashscreen`.
- **Custom app icon**: adaptive icon built from `ic_launcher_background.xml` / `ic_launcher_foreground.xml`, same mark.

## How to open
1. Open Android Studio (Koala/Ladybug or newer recommended).
2. `File > Open` and select this project's root folder (the one containing `settings.gradle.kts`).
3. Let Gradle sync (requires network access the first time).
4. Run on an emulator or device with **API 26+**.

## Project structure
```
app/src/main/java/com/example/moodjournal/
  MainActivity.kt              – bottom-nav shell, splash, modal trigger
  data/MoodEntry.kt            – Mood enum + MoodEntry model
  data/MoodRepository.kt       – SharedPreferences-backed storage (entries + prefs)
  ui/LogFragment.kt            – mood grid + note + save
  ui/HistoryFragment.kt        – RecyclerView of past entries
  ui/SettingsFragment.kt       – preference storage UI
  ui/InfoDialogFragment.kt     – the modal info view
  ui/MoodAdapter.kt            – RecyclerView adapter
app/src/main/res/
  layout/                      – activity_main, fragment_log, fragment_history,
                                  fragment_settings, item_mood_entry, dialog_info
  drawable/ic_launch_symbol.xml, ic_launcher_*.xml – custom art
```
