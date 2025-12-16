# Rayfield UI Library Documentation

Rayfield is a Roblox UI library developed and maintained by **Sirius**.  
It focuses on clean design, ease of use, and a consistent API.

> **Official Source**  
> The **ONLY** official GitHub account for Rayfield is:  
> https://github.com/sirius-menu  
>  
> Any other uploads or mirrors are unofficial.

---

## Overview

Rayfield uses a **window → tab → element** structure.

- A **Window** holds everything
- **Tabs** organize content
- **UI Elements** (buttons, toggles, sliders, etc.) live inside tabs

This documentation covers the most commonly used features of Rayfield.

---

## Creating Tabs

### Function
```lua
Window:CreateTab("Tab Name")
```

### Description
Creates a new tab inside the Rayfield window.

### Example
```lua
local Tab = Window:CreateTab("Main Tab")
```

---

## Buttons

### Function
```lua
Tab:CreateButton({...})
```

### Description
Creates a clickable button that runs a callback when pressed.

### Example
```lua
Tab:CreateButton({
    Name = "Example Button",
    Callback = function()
        print("Button clicked")
    end
})
```

---

## Toggles

### Function
```lua
Tab:CreateToggle({...})
```

### Description
Creates a toggle switch that can be turned on or off.

### Example
```lua
Tab:CreateToggle({
    Name = "Enable Feature",
    CurrentValue = false,
    Callback = function(Value)
        print(Value)
    end
})
```

`Value` returns `true` or `false` depending on the toggle state.

---

## Sliders

### Function
```lua
Tab:CreateSlider({...})
```

### Description
Creates a slider for selecting numeric values.

### Example
```lua
Tab:CreateSlider({
    Name = "WalkSpeed",
    Range = {0, 100},
    Increment = 1,
    CurrentValue = 16,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end
})
```

---

## Dropdowns

### Function
```lua
Tab:CreateDropdown({...})
```

### Description
Creates a dropdown menu with selectable options.

### Example
```lua
Tab:CreateDropdown({
    Name = "Select Option",
    Options = {"Option 1", "Option 2", "Option 3"},
    CurrentOption = {"Option 1"},
    Callback = function(Option)
        print(Option)
    end
})
```

---

## Keybinds

### Function
```lua
Tab:CreateKeybind({...})
```

### Description
Creates a keybind that triggers a callback when pressed.

### Example
```lua
Tab:CreateKeybind({
    Name = "Toggle UI",
    CurrentKeybind = "RightShift",
    Callback = function()
        print("Keybind pressed")
    end
})
```

---

## Text Inputs

### Function
```lua
Tab:CreateInput({...})
```

### Description
Creates a text input box.

### Example
```lua
Tab:CreateInput({
    Name = "Username",
    PlaceholderText = "Enter text here",
    RemoveTextAfterFocusLost = false,
    Callback = function(Text)
        print(Text)
    end
})
```

---

## Paragraphs

### Function
```lua
Tab:CreateParagraph({...})
```

### Description
Displays static text information.

### Example
```lua
Tab:CreateParagraph({
    Title = "Information",
    Content = "This is an example paragraph."
})
```

---

## Labels

### Function
```lua
Tab:CreateLabel("Text")
```

### Description
Creates a simple text label.

### Example
```lua
Tab:CreateLabel("Rayfield UI Library")
```

---

## Notifications

### Function
```lua
Rayfield:Notify({...})
```

### Description
Displays a notification on screen.

### Example
```lua
Rayfield:Notify({
    Title = "Notification",
    Content = "This is a message",
    Duration = 5,
    Image = 4483362458
})
```

---

## Configuration System

Rayfield supports saving and loading configurations.

### Example
```lua
Rayfield:LoadConfiguration()
Rayfield:SaveConfiguration()
```

Configurations allow users to keep their UI settings between sessions.

---

## Typical Structure

```lua
local Tab = Window:CreateTab("Main")

Tab:CreateToggle({
    Name = "Example Toggle",
    CurrentValue = false,
    Callback = function(Value)
        print(Value)
    end
})

Tab:CreateButton({
    Name = "Example Button",
    Callback = function()
        print("Clicked")
    end
})
```

---

## Notes

- All UI elements must be created inside tabs
- Callbacks run locally
- Rayfield is intended for clean and readable scripts

---

## Official Information

Rayfield is developed by **Sirius**.

Official GitHub repository:  
https://github.com/sirius-menu  

This is the **ONLY** official GitHub account for Rayfield.
