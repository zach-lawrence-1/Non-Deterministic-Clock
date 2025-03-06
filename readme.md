# Non Deterministic Text Clock
## Inspiration
- https://www.youtube.com/watch?v=plFwBqBYpcY
## Description
A real time clock displayed in the terminal in a fancy way. Uses random text generation to act as the background, and the clock numbers themselves with color included. The code files clock_shapes.cpp, clock_time.cpp, and random_text.cpp are modified and combined into ND_clock.cpp to create the final display.
## How To Run
### Downloading The Code
Download the code and make file as follows
Git:
1. ```git clone https://github.com/zach-lawrence-1/Non-Deterministic-Clock.git c```
   - c can be any local directory you want.
2. ```cd c```

OR

Just download zip from github and unzip where you want
### Windows
On windows, as long as you have MSYS2 setup with g++ and you can run make files then you should be able to run the main program clock_ND.cpp as follows:
1. Download code and make file.
2. Open a terminal in the same directory as the code and make file.
3. Type in ```make ND```
4. run ```./ND.exe``` or ```./ND```
### Linux
As long as you have g++ and make installed and running on your linux box, you should be able to run the main program as follows:
1. Open a terminal in the same directory as the code and make file or just navigate there via cd commands.
2. Type in ```make ND```
3. run ```./ND```

You can also run ```make ct```, ```make random```, ```make shapes``` and execute the associated executable/elf files to run the individual pieces I broke the problem into if you want.

## Time Complexity Analysis
```string RandomBlockGenerator()``` **O(1)**  
Since the size of our random string is fixed. If the random string was a block of size n * m, then it would be **O(n*m)**

```void ExtractCurrentTime(int clockDigits[8])``` **O(1)**  

``void PrintClock(unsigned long int clock[11], int clockDigits[8], std::string &textBlock)``` **O(n)**  
Since insert function has **O(n)** time complexity and arrays/strings are fixed size. If we have a random string of size n * m, and our clock digits had a width of k then our time complexity would be **O(m*k + m*n)**. This is because we would loop through the height of the string m, and use insert function m times as well loop through k extracted bits in that height loop.

## Updates
1. Got idea/inspired and wrote random text generator which generates a fixed size block of random characters, then wrote a basic clock using ctime.
2. Implemented a basic idea of how I want to display the clock text and color scheme.
3. Clock now kind of works, but it is crooked. I need to fix some unknown spacing issue.
<img width="479" alt="crooked_clock" src="https://github.com/user-attachments/assets/39998e3b-c131-461c-a308-7393b589ed77" />

4. Clock is now working correctly.
<img width="517" alt="basic_working_clock" src="https://github.com/user-attachments/assets/684d1bbb-413d-42b7-9f09-55d3e17eaf44" />

5. Clock is now cross platform between windows and linux, I have no way of testing for mac so idk if it works there.
![image](https://github.com/user-attachments/assets/a4d12e42-92a8-44bb-9081-858b4f502e05)
