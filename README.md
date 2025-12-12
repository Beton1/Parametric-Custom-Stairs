# FreeCAD Parametric Stairs Macro

A **FreeCAD macro** for generating **parametric stairs** from a **path** and a **closed sketch**. This new approach allows you to create complex stair geometries — straight, curved, or irregular — directly from a user‑defined path.

---

## 🚀 Overview

The macro automates stair generation by combining two key inputs:
1. A **closed sketch or wire** that defines the overall stair footprint (shape and width).  
2. A **path** made up of connected lines that define the stair’s progression and alignment.

Using these references, the macro constructs the stair geometry along the defined path, using the shape of the closed sketch as the stair’s cross‑section.

![Stairs example](<images/Pasted Layer.png>)

---

## ✨ Features

- Generate stairs from a **path** and a **closed sketch** (FreeCAD Sketch or Draft wire).  
- Compatible with **straight**, **curved**, or **custom‑shaped** stair layouts.
- **"Align"** option for handling orientation errors (choose `left` or `right`).  
- Automatically adapts to changes in the defining path or sketch.  
- Works across **Part**, **Draft**, and **Arch** workbenches.

---

## ⚙️ How It Works

1. Create a **closed sketch** that represents the stair outline (top view).  
2. Within that sketch, draw one or more **path lines** following the logical stair direction — from **start** to **finish**.  
3. Make sure the **stair path** runs continuously along the full stair length.  
4. Select both the **closed wire/sketch** and the **path edges**.  
5. Run the macro (`Macro → Macros → CurvedPathStairs.FCMacro`).  
6. The macro will generate a parametric stair aligned to the chosen path and shaped according to the closed sketch.

If the geometry appears inverted or misaligned, toggle the **`align`** property between `"left"` and `"right"` and re‑run the macro.

---

## 🧩 Requirements

- **FreeCAD 0.21** or newer  
- **Draft**, **Part**, or **Arch** workbench installed  
- Works on **Windows**, **Linux**, and **macOS**

---

## 🧱 Installation

1. Download or clone this repository.  
2. Copy `StairsFromPath.FCMacro` to your FreeCAD macros folder:  
   - **Linux:** `~/.local/share/FreeCAD/Macro/`  
   - **Windows:** `%APPDATA%\FreeCAD\Macro\`  
   - **macOS:** `~/Library/Preferences/FreeCAD/Macro/`  
3. Launch FreeCAD → `Macro → Macros...` → select `CurvedPathStairs` → **Run**.

---

## 🛠 Development Notes

- The macro is **fully functional**, but still **under polishing**.  
- It was further refined by the members of the FreeCAD community, and you can find other versions of the macro in the forum discussion [Custom Stair Forum](https://forum.freecad.org/viewtopic.php?style=5&t=58317).  
- Internally, the macro computes intermediate step planes along the path using `Part` and `Draft` APIs, extrudes the sketch profile along these planes, and merges them into a solid result.

---

## 👥 Contributors

- **Beton1** – Macro creator and main developer  
- **Roy_043** – Bug fixes, performance improvement(great speed up, stairs a generated in 6.25sec instead of the original 24.77sec) and testing
- **paullee** – Bug fixes, performance improvement(another great speed up, generation time went down to 1.52sec) and testing   
- **balrobs** – Extensive testing and feedback

---

## 💬 Community Feedback

This macro was developed with active feedback from the FreeCAD community. It has been tested by architects and users on the official forum:

> "I tried your Macro and I can say it's cool stuff. Compliments to you and thank you for picking up this challenge."  
> — *FreeCAD Forum User*

> "Excellent! I just tried your amazing work :D I tested different types of the stairs...but as you already know, it takes some time to build them. For the rest, everything worked fine and without any major problem."  
> — *Community Member*

> "Today I used your macro to model an oval stair. Amazing stuff! :D"  
> — *Community Member*

[View the full discussion thread on the FreeCAD Forum →](https://forum.freecad.org/viewtopic.php?t=58317)

## 🧾 License

This project is released under the **MIT License**.  
You may use, modify, and distribute this macro freely with attribution.

---

## 🤝 Contributing

Contributions are welcome!  
You can help by:
- Improving the GUI  
- Enhancing geometry alignment  
- Adding support for landings, railings, or complex profiles  
- Testing on different FreeCAD versions  

Create a **pull request** or **issue** if you find bugs or have ideas for enhancements.

---

## 📸 Example

| Closed sketch and path | Generated parametric stairs |
|------------------------|-----------------------------|
| ![Input example](docs/path_sketch_example.png) | ![Generated stair](docs/generated_stair.png) |
