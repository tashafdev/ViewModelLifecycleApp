# ViewModelLifecycleApp

A simple Android project demonstrating the lifecycle of ViewModel and its integration with Jetpack Compose for managing UI-related data across configuration changes like screen rotations.

## Key Concepts Covered

### 1. **What is a ViewModel?**
A **ViewModel** is a lifecycle-aware component in the MVVM pattern. It holds and manages UI-related data, keeping UI logic separate from UI code. A ViewModel survives configuration changes and provides a way to handle data that is displayed on the UI.

#### Responsibilities:
- Acts as a bridge between the **View** (UI) and the **Model** (data).
- Prepares and formats data for display on the UI.
- Reacts to user events and updates the UI state.
- Retains state across configuration changes (e.g., screen rotation).

**Analogy**: Think of the ViewModel as a **smart assistant** that fetches raw data, formats it, and communicates with the UI on what needs to be displayed.

### 2. **Lifecycle and Retaining State**
- **Survives Configuration Changes**: A ViewModel retains its state during screen rotations or any other configuration changes. It prevents the need to reload data every time the activity or fragment is recreated.
  
- **Binding with Jetpack Compose**: The project demonstrates how to use `viewModel()` in Jetpack Compose to bind the ViewModel to Composables.

#### Best Practices:
- Use `by viewModels()` or `viewModel()` in Compose to get a lifecycle-aware instance of ViewModel.
- Avoid referencing Views or Contexts inside the ViewModel to prevent memory leaks.
- For ViewModels that need constructor parameters, use a `ViewModelProvider.Factory` to inject dependencies.

### 3. **Process Death and ViewModel**
In Android, **process death** occurs when the system kills your app’s process to reclaim resources. This causes the in-memory ViewModel to be cleared. To restore UI-related state after process death, we use **SavedStateHandle**, which is tied to the ViewModel and helps retain small pieces of state.

### 4. **Use Cases for ViewModel**
- **State Management**: ViewModels are particularly useful for handling UI-related state that should persist across configuration changes like user input, selections, or lists.
- **Separation of Concerns**: By separating the UI logic from the business logic and data handling, ViewModels provide a cleaner architecture and improve maintainability.

## Features

- **Counter App**: Demonstrates how a simple counter is retained across configuration changes using ViewModel.
- **Jetpack Compose**: Shows how ViewModel is integrated with Jetpack Compose to bind the ViewModel to Composables and manage UI state.
  
## Key Libraries Used

- `androidx.lifecycle.ViewModel`
- `androidx.lifecycle.SavedStateHandle`
- Jetpack Compose for UI management

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/tashafdev/ViewModelLifecycleApp.git
