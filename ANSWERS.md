# GitHub Repository

https://github.com/kikaykaye/flutter_basics_lab

---

# Review Questions — Flutter Basics Lab

### 1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each from this lab.

A `StatelessWidget` does not manage changing state, while a `StatefulWidget` can update its interface when its state changes. In Activity 1, `ProfileCard` is a StatelessWidget because its displayed information stays the same. In Activity 2, `WaterTrackerPage` is a StatefulWidget because the number of glasses changes when the user taps the buttons.

### 2. Why is a StatefulWidget written as two classes? What does each class do?

A `StatefulWidget` uses two classes to separate the widget's configuration from its changing state. The first class defines the widget and creates its State object. The second class stores changing data, handles updates, and builds the interface again when the state changes.

### 3. In Activity 2, what happened when you changed `_glasses` outside `setState()`? Why?

When I moved _glasses++ outside setState(), I learned that changing a variable alone does not notify Flutter to rebuild the interface. Calling setState() tells Flutter to rebuild the widget so the updated value can appear on the screen. I then restored the increment inside setState().

### 4. Looking at the Debug Console in Activity 2, when is `build()` called?

The `build()` method is called when the widget is first displayed and whenever Flutter rebuilds it. In Activity 2, tapping the plus, minus, or Reset button calls `setState()`, which requests a rebuild so the screen can display the updated number of glasses.

### 5. Explain the main axis and the cross axis of a Row and of a Column.

In a `Row`, the main axis is horizontal and the cross axis is vertical. In a `Column`, the main axis is vertical and the cross axis is horizontal. The main axis controls the direction in which children are arranged, while the cross axis controls their alignment across that direction.

### 6. In Activity 3, what happened when you removed `Expanded` from a StatBox? What does `Expanded` do?

Removing `Expanded` from one `StatBox` allowed it to take its natural width instead of sharing the available row space equally with the other boxes. This could make the boxes uneven or cause an overflow, depending on the available width. `Expanded` makes a child fill its share of the remaining space in a `Row` or `Column`.

### 7. Why do we use `GridView.builder` for the menu instead of a Column with many children?

We use `GridView.builder` because it arranges menu items in a grid and supports scrolling when there are more items than fit on the screen. It also creates items as needed, making it more suitable for a menu with many items than a single long `Column`.

### 8. How do `Stack` and `Positioned` create the Best seller badge in Activity 4?

`Stack` allows widgets to overlap inside a menu card. `Positioned` specifies where the Best seller badge should appear within the stack, such as near the top-left corner. This places the badge over the menu item's content.

### 9. What is the difference between customizing with `ThemeData` and with a style on one widget? Give one example of each from Activity 5.

`ThemeData` defines shared styling for the application, while a style applied to one widget customizes that particular component. In Activity 5, `buildTheme()` sets the app's color scheme and text theme, while the Elevated button's style sets its corner radius to 20, making its corners more rounded.

### 10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the change reach `MaterialApp`?

The `_ThemeDemoAppState` class holds the `_isDark` variable. When the switch changes, `setState()` updates the variable and rebuilds `ThemeDemoApp`. The updated value is then used by `MaterialApp` through its `themeMode` property to select either the light or dark theme.

## Last Three `build()` Called Lines

```text
build() called: 1 glasses
build() called: 2 glasses
build() called: 3 glasses
``` 