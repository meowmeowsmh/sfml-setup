🎮 SFML Setup Guide for VSCode on Windows
A complete step-by-step guide to set up SFML 3.1.0 with VSCode on Windows.

📋 Prerequisites
If you don't have a C++ compiler installed, watch this first:
🔗 Install MinGW on Windows

📥 Step 1: Download SFML
Go to SFML Download Page

Download the correct version for VSCode/MinGW:

GCC 14.2.0 MinGW (SEH) (UCRT) - 64-bit (74.3 MB)

📂 Step 2: Extract SFML
Extract the zip file to a simple path (avoid spaces in folder names):

Recommended location:

text
D:\SFML\SFML-3.1.0\
You can use C:, D:, or any drive you prefer

⚙️ Step 3: Configure VSCode
Create a .vscode folder in your project directory and add these files:

📄 .vscode/c_cpp_properties.json
json
{
    "configurations": [
        {
            "name": "Win32",
            "includePath": [
                "${workspaceFolder}/**",
                "D:/SFML/SFML-3.1.0/include"
            ],
            "defines": [],
            "compilerPath": "C:/msys64/ucrt64/bin/g++.exe",
            "cStandard": "c17",
            "cppStandard": "c++17",
            "intelliSenseMode": "windows-gcc-x64"
        }
    ],
    "version": 4
}
📄 .vscode/tasks.json
json
{
    "tasks": [
        {
            "type": "cppbuild",
            "label": "C/C++: g++.exe build active file",
            "command": "C:\\msys64\\ucrt64\\bin\\g++.exe",
            "args": [
                "-fdiagnostics-color=always",
                "-g",
                "${file}",
                "-o",
                "${fileDirname}\\${fileBasenameNoExtension}.exe",
                "-I",
                "D:\\SFML\\SFML-3.1.0\\include",
                "-L",
                "D:\\SFML\\SFML-3.1.0\\lib",
                "-lsfml-graphics",
                "-lsfml-window",
                "-lsfml-system"
            ],
            "options": {
                "cwd": "${fileDirname}"
            },
            "problemMatcher": ["$gcc"],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ],
    "version": "2.0.0"
}
🔧 Step 4: Adjust Paths (If Needed)
If your SFML is in a different location, update these paths:

File	Line to Change	Format Example
c_cpp_properties.json	Include path	"D:/SFML/SFML-3.1.0/include"
tasks.json	Include path	"D:\\SFML\\SFML-3.1.0\\include"
tasks.json	Library path	"D:\\SFML\\SFML-3.1.0\\lib"
Note: Use forward slashes / in c_cpp_properties.json and double backslashes \\ in tasks.json

🚀 Step 5: Compile and Run
Option A: Using VSCode
Open your .cpp file

Press Ctrl+Shift+B to build

Run with .\yourgame.exe in the terminal

Option B: Using Command Line
Dynamic Linking (requires DLLs):

bash
g++ mygame.cpp -o mygame.exe -I"D:\SFML\SFML-3.1.0\include" -L"D:\SFML\SFML-3.1.0\lib" -lsfml-graphics -lsfml-window -lsfml-system
Static Linking (standalone .exe - no DLLs needed):

bash
g++ mygame.cpp -o mygame.exe -I"D:\SFML\SFML-3.1.0\include" -L"D:\SFML\SFML-3.1.0\lib" -lsfml-graphics-s -lsfml-window-s -lsfml-system-s -lopengl32 -lfreetype -lwinmm -lgdi32 -static-libgcc -static-libstdc++
📺 Video Tutorials
Topic	Link
Install MinGW	Watch here
SFML Setup Guide	Watch here
🧪 Test Your Setup
Create a test.cpp file:

cpp
#include <SFML/Graphics.hpp>

int main()
{
    sf::RenderWindow window(sf::VideoMode({800, 600}), "SFML Test");
    
    while (window.isOpen())
    {
        while (const std::optional event = window.pollEvent())
        {
            if (event->is<sf::Event::Closed>())
                window.close();
        }
        
        window.clear();
        window.display();
    }
    
    return 0;
}
If you see a window appear → Setup successful! ✅

