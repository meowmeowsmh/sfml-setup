# SFML-setup
requirements if not downloaded c++: https://youtu.be/1PBD5qFWdq8?si=vBquJuB2iuzFXl8h

the special extra instruction is to uncompress the file a put it where it's belong d: c: e: go to the c_cpp_properties.json and tasks.json to change the direcotory 

you can use deepseek to help to configure you current setup

https://www.sfml-dev.org/download/sfml/3.1.0/ go to this website and download what currently you are using vscode or etc

unfortunately my setup only worked in vscode

"D:/SFML/SFML-3.1.0/include"   // Look here for SFML headers 
find the include path from the sfml directory can change SFML/SFML-3.1.0
D: same goes to this 

Example: 
change this also then your setup only required this 
        "D:\\SFML\\SFML-3.1.0\\include", <- change the directory name to your current path if video needed 
        "-L",
        "D:\\SFML\\SFML-3.1.0\\lib",
cmd in your vscode:
        g++ mygame.cpp -o mygame.exe -I"D:\SFML\SFML-3.1.0\include" -L"D:\SFML\SFML-3.1.0\lib" -lsfml-graphics-s -lsfml-window-s -lsfml-system-s -lopengl32 -lfreetype -lwinmm -lgdi32 -static-libgcc -static-libstdc++

video that help me setup: https://youtu.be/rZE700aaT5I?si=8DutHdoP3atzB8Gn
        
good luck!!!!
