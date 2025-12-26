# Noor Companion – MVP Backlog

---

## Project & Design

### Project Initialization
- **Goal:** Set up Android project with Kotlin + Jetpack Compose
- **Tasks:**
  - Configure Gradle, Compose, Navigation, ViewModel
  - Add DataStore for offline caching
  - Configure dark mode
  - Enable RTL support (`android:supportsRtl="true"`)
- **Notes:** Foundation for all MVP features

### Design System
- **Goal:** Maintain consistent UI/UX
- **Tasks:**
  - Define color palette (soft green, beige)
  - Define typography (Arabic font for content)
  - Wireframe main screens (Home, Prayer, Hadith, Dhikr, Calendar, Asmaul Husna)
  - Create reusable Compose components (cards, lists, buttons)

---

## Prayer Times + Advanced Night Timings

### Display Daily Prayer Times
- **Goal:** Show Fajr, Dhuhr, Asr, Maghrib, Isha
- **API:** [Aladhan API](https://aladhan.com/prayer-times-api)
- **Tasks:**
  - Fetch prayer times by GPS or city
  - Display in user-friendly format
  - Support Arabic + English

### Advanced Night Timings
- **Goal:** Show Midnight, First Third, Middle, Last Third (for Tahajjud)
- **Tasks:**
  - Calculate based on Isha → Fajr interval
  - Display times on Prayer Screen
  - Optional notification

### Schedule Prayer Notifications
- **Goal:** Remind user of prayers and night timings
- **Tasks:**
  - Use WorkManager or AlarmManager for local notifications
  - Allow user to toggle notifications
  - Respect device timezone

### Offline Caching of Prayer Times
- **Goal:** App works without internet
- **Tasks:**
  - Cache daily timings in DataStore
  - Show cached data if API fails

---

## Hadith of the Day

### Display Daily Random Hadith
- **Goal:** User learns a Hadith each day
- **API:** Public Hadith APIs ([GitHub sources](https://github.com/alihmada/Islamic-APIs))
- **Tasks:**
  - Fetch random Hadith daily
  - Show Arabic + English translation
  - Cache last Hadith for offline

### Bookmark Favorite Hadith
- **Goal:** Easy reference of important Hadith
- **Tasks:**
  - Save favorite Hadith in DataStore
  - Provide a “Favorites” screen

---

## Dhikr & Adhkar

### Display Morning & Evening Dhikr
- **Goal:** Guide user through daily worship
- **Data Source:** Local JSON asset
- **Tasks:**
  - Load morning/evening lists
  - Show Arabic + English
  - Allow scrolling

### Mark Favorites
- **Goal:** User can quickly access preferred Dhikr
- **Tasks:**
  - Save favorites in DataStore
  - Optional filtering

### Schedule Dhikr Notifications
- **Goal:** Remind user to recite Dhikr
- **Tasks:**
  - Schedule local notifications for morning/evening

---

## Hijri Calendar & Islamic Events

### Display Hijri & Gregorian Dates
- **Goal:** Users follow Islamic dates accurately
- **API:** [Aladhan API `gToH`](https://aladhan.com/prayer-times-api) or UmmahAPI
- **Tasks:**
  - Show today’s Hijri date + Gregorian
  - Support Arabic + English

### Display Islamic Events / Holidays
- **Goal:** Notify user of upcoming Islamic events
- **Tasks:**
  - Fetch events from API or local dataset
  - Highlight special days

### Offline Access for Calendar
- **Goal:** App functional without internet
- **Tasks:**
  - Cache last fetched dates/events

---

## 99 Names of Allah (Asmaul Husna)

### Daily Name of Allah
- **Goal:** Help user memorize one name daily
- **Data Source:** Local JSON or UmmahAPI
- **Tasks:**
  - Show today’s name + meaning
  - Arabic + English

### View Full List of Names
- **Goal:** Study all 99 names anytime
- **Tasks:**
  - Scrollable list with search
  - Arabic + English translation

### Bookmark Favorite Names
- **Goal:** User can save preferred names
- **Tasks:**
  - Save favorites in DataStore
  - Display in “Favorites” screen

### Daily Reminder for Name of the Day
- **Goal:** Reinforce learning
- **Tasks:**
  - Local notification for daily name

---

## General Features

### Dark Mode Support
- **Goal:** Comfortable reading at night
- **Tasks:**
  - Detect system theme
  - Allow manual toggle

### Language Switcher
- **Goal:** Switch between Arabic and English
- **Tasks:**
  - Add settings screen
  - Reload UI strings dynamically
  - Support RTL/LTR layout

### Offline Mode
- **Goal:** App fully usable without internet
- **Tasks:**
  - Cache all API responses (prayer, Hadith, Hijri, Asmaul Husna)
  - Fallback to local JSON if API fails

---

## Testing & QA

### Unit Tests
- Test ViewModel logic, night timing calculations

### UI Tests
- Verify Compose screen navigation
- Validate text rendering in Arabic + English

### Notification Tests
- Ensure all prayer, Dhikr, and Name-of-the-Day notifications fire correctly

### Offline Testing
- Verify app works without internet and shows cached data

---

## Notes / Ideas
- **APIs used:**
  - Aladhan → Prayer + Hijri
  - UmmahAPI → optional Qibla + Asmaul Husna
  - Hadith API (public JSON) → daily Hadith
- **Goals:**
  - Minimalist, calm design
  - Bilingual (Arabic + English)
  - Offline-first
  - Useful for daily worship and reflection
