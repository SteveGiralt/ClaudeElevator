# Elevator Simulator

A visual elevator simulation built with Kotlin/WASM and Compose Multiplatform. The application renders an interactive elevator shaft with animated car movement, doors, and a button panel.

## Features

- **Visual Elevator Shaft**: 6-floor shaft with labeled floors displayed as filled rectangles
- **Animated Elevator Car**: Amber/gold car with gray doors that shrink open and grow closed
- **Smooth Animations**: Eased movement (2 seconds per floor) and door animations (0.5 seconds)
- **SCAN Algorithm**: Elevator services floors using the classic elevator algorithm (continues in current direction, then reverses)
- **Internal Button Panel**: Click floor buttons inside the elevator to queue destinations; buttons light up when selected and can be toggled off
- **External Call Buttons**: Up/down call buttons next to each floor of the shaft
  - Floor 1 has only an up button; Floor 6 has only a down button
  - Buttons light up amber when pressed and cannot be canceled
  - Aligned vertically with corresponding floors in the shaft
- **Directional Awareness**: Elevator only stops for call buttons when traveling in the matching direction (up calls answered when going up, down calls when going down)
- **Direction Indicator**: Arrow displays on the car showing the travel direction; clears when no destination is queued
- **Auto-Return**: Elevator returns to floor 1 with doors open after 5 seconds of idle time

## Requirements

- JDK 17 or higher
- Gradle 8.x (included via wrapper)

## Build and Run

1. Clone the repository and navigate to the project directory

2. Start the development server (Windows):
   ```
   .\gradlew wasmJsBrowserDevelopmentRun
   ```
   Or:
   ```
   .\gradlew.bat wasmJsBrowserDevelopmentRun
   ```

3. Open your browser to http://localhost:8088

## Project Structure

- `src/wasmJsMain/kotlin/Main.kt` - Main application code including elevator logic and UI components
- `src/wasmJsMain/resources/index.html` - HTML entry point
- `build.gradle.kts` - Gradle build configuration

## Technology Stack

- Kotlin/WASM
- Compose Multiplatform
- Material 3 Design
