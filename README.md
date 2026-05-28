📥 Download SFML
Go to: SFML 3.1.0 Download Page

Choose the correct version for VSCode/MinGW:

GCC 14.2.0 MinGW (SEH) (UCRT) - 64-bit (74.3 MB)

📂 Extract to Any Drive
Extract the zip file to a simple path without spaces:

Examples:

text
D:\SFML\SFML-3.1.0\
C:\SFML\SFML-3.1.0\
E:\SFML\SFML-3.1.0\
⚙️ Configure Your Paths
You need to update two files in your .vscode folder:

1. c_cpp_properties.json
Change the includePath to your SFML location:

json
"D:/SFML/SFML-3.1.0/include"
2. tasks.json
Change these two paths to your SFML location:

json
"-I",
"D:\\SFML\\SFML-3.1.0\\include",
"-L",
"D:\\SFML\\SFML-3.1.0\\lib"
🚀 Compile Command
bash
g++ mygame.cpp -o mygame.exe -I"D:\SFML\SFML-3.1.0\include" -L"D:\SFML\SFML-3.1.0\lib" -lsfml-graphics-s -lsfml-window-s -lsfml-system-s -lopengl32 -lfreetype -lwinmm -lgdi32 -static-libgcc -static-libstdc++
📺 Need Help?
MinGW Installation: Watch here

SFML Setup: Watch here

Use DeepSeek AI to help configure your specific setup

⚠️ Important
Note: This setup only works in VSCode with proper configuration. Adjust the drive letter (C:, D:, E:) based on where you extracted SFML.

Good luck! 🎯

