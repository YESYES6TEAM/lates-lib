a ui library i made in like a day lol

![image](https://github.com/user-attachments/assets/9221bd33-abf3-4aae-9576-419a86d14068)

📘 Lates-UI Library Documentation

A simple guide for building UI using the Lates Library.


---

# 📦 Initialization

Load the Library
```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/lxte/lates-lib/main/Main.lua"))()
```
# Create a Window
```lua
local Window = Library:CreateWindow({
    Title = "???",
    Theme = "Dark",
    Size = UDim2.fromOffset(570, 370),
    Transparency = 0.2,
    Blurring = true,
    MinimizeKeybind = Enum.KeyCode.LeftAlt
})
```
Window Properties

Property	Description

Title	Window title text
Theme	Name of selected theme
Size	Window size (UDim2)
Transparency	UI transparency (0–1)
Blurring	Enables background blur
MinimizeKeybind	Keybind that hides/shows UI



---

# 🎨 Themes

You may define and apply themes manually:

Window:SetTheme(Themes.Dark)

Theme tables require:

Frames colors

Text colors

Outline colors

Icon colors


Example theme structure:
```lua
ThemeName = {
    Primary = Color3.new(),
    Secondary = Color3.new(),
    Component = Color3.new(),
    Interactables = Color3.new(),

    Tab = Color3.new(),
    Title = Color3.new(),
    Description = Color3.new(),

    Shadow = Color3.new(),
    Outline = Color3.new(),

    Icon = Color3.new(),
}
```

---

# 📑 Tabs & Sections

# Add Tab Sections
```lua
Window:AddTabSection({
    Name = "Main",
    Order = 1
})
```
# Cplreate a Tab
```lua
local Main = Window:AddTab({
    Title = "Components",
    Section = "Main",
    Icon = "rbxassetid://11963373994"
})
```
# Add a Section Divider
```lua
Window:AddSection({
    Name = "Non Interactable",
    Tab = Main
})
```

---

# 📄 Paragraph
```lua
Window:AddParagraph({
    Title = "Paragraph",
    Description = "Insert any important text here.",
    Tab = Main
})
```

---

# 🔘 Button
```lua
Window:AddButton({
    Title = "Button",
    Description = "I wonder what this does",
    Tab = Main,
    Callback = function()
        Window:Notify({
            Title = "hi",
            Description = "i'm a notification",
            Duration = 5
        })
    end
})
```

---

# 🎚 Slider
```lua
Window:AddSlider({
    Title = "Slider",
    Description = "Sliding",
    Tab = Main,
    MaxValue = 100,
    Callback = function(Value)
        warn(Value)
    end
})
```

---

# ✔ Toggle
```lua
Window:AddToggle({
    Title = "Toggle",
    Description = "Switching",
    Tab = Main,
    Callback = function(State)
        warn(State)
    end
})
```

---

# ⌨ Input Box

```lua
Window:AddInput({
    Title = "Input",
    Description = "Typing",
    Tab = Main,
    Callback = function(Text)
        warn(Text)
    end
})
```


---

# 📥 Dropdown
```lua
Window:AddDropdown({
    Title = "Dropdown",
    Description = "Selecting",
    Tab = Main,
    Options = {
        ["An Option"] = "hi",
        ["And another"] = "hi",
        ["Another"] = "hi",
    },
    Callback = function(Value)
        warn(Value)
    end
})
```
