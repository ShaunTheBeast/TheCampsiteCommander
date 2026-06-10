# TheCampsiteCommander🏕️

Campsite Commander is an intuitive Android utility application designed to help campers efficiently log, track, and manage their packing inventory. Built entirely natively utilizing **Jetpack Compose**, the app ensures dynamic UI state updates and fluent screen transitions.

---

## 🚀 Features

* **Timed Splash Screen:** A seamless brand experience upon application launch using Jetpack Compose side-effects.
* **Dual-Screen Navigation:** Uses the Jetpack Navigation component to split actions between Inventory Input (`MainScreen`) and Inventory Overview (`ViewScreen`).
* **Dynamic State Hoisting:** Keeps your data persistent across views using architecture-optimized `mutableStateListOf`.
* **Intelligent Inventory Accumulation:** Automatically checks if an item name already exists; if found, it aggregates the quantities rather than creating a duplicate entry.
* **Live Metrics:** Computes real-time totals of items currently packed at the tap of a button.
* **Safe Type Parsing:** Features a graceful fallback parser to handle mismatches between raw string inputs and data structural Enums (`RssCategory`).

---

## 🛠️ Architecture & Tech Stack

* **Language:** Kotlin
* **UI Framework:** Jetpack Compose (Declarative UI)
* **Navigation:** `androidx.navigation:navigation-compose`
* **Asynchronous Processing:** Kotlin Coroutines (`LaunchedEffect` / `delay`)
* **Design Paradigm:** State Hoisting for clean separation of UI elements and state retention.

---

## 📈 State Management Flow

The application relies heavily on hoisted states within the `MyApp()` wrapper layout. 

```text
         [ MyApp ] <-- Holds Global State Arrays (gearList, quantityList, etc.)
          / \
         / \
  [MainScreen] [ViewScreen]
  (Mutates) (Read-Only Display)
