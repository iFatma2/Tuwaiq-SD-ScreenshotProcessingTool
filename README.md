

# Screenshot Processing Tool (C# + SkiaSharp)

## Overview
This project is a simple C# console tool designed to demonstrate how different layers of a system connect — from hardware-level interactions provided by the operating system, to higher-level image processing libraries like **SkiaSharp**.

The goal is to understand both **vertical** and **horizontal** integration inside real applications.

---

## Vertical Integration (OS / Hardware Layer)
Vertical integration refers to features that interact closely with the operating system and indirectly with hardware, such as:

- Capturing the screen using macOS's built-in `screencapture` tool  
- Managing files and directories through the filesystem  
- Running OS commands using `ProcessStartInfo`

This is the “bottom-up” path:  
hardware → OS → your code.

---

## Horizontal Integration (Library Layer)
Horizontal integration focuses on how your application connects to multiple libraries that operate at the same level, providing different specialized functions:

- **SkiaSharp** for image decoding, pixel manipulation, and encoding  
- **System.IO.Compression** for creating ZIP archives  
- Working with different file formats and utilities side-by-side  

This is the “side-by-side” layer where libraries collaborate inside your app.

---

## What the App Does
1. Captures a screenshot using the macOS `screencapture` command.  
2. Loads the screenshot into SkiaSharp.  
3. Converts the image to grayscale.  
4. Flips the image horizontally.  
5. Saves the processed image to the Desktop.  
6. Creates a ZIP file containing the output image.

The idea is to clearly see how data moves across layers:

- **Vertical:** OS → your program → file output  
- **Horizontal:** your code ↔ SkiaSharp ↔ Compression library

---

## Why This Matters
This project shows how to:

- Use OS-level tools inside a C# application  
- Manipulate images at the pixel level  
- Combine multiple components into a clean workflow  
- Build a small end-to-end pipeline: capture → process → save → compress  

It’s a practical way to understand how real tools communicate across system layers.

---

## Requirements
- macOS  
- .NET SDK  
- SkiaSharp NuGet package  

Install SkiaSharp:
```bash
dotnet add package SkiaSharp
