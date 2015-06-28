อุปกรณ์

1. Arduino Board
2. Temperature and Humidity sensor SHT11
3. OLED Display ssd1306 128x64

Installation 

ก่อนอื่นต้องติดตั้ง library ให้กับ Arduino ก่อน ซึ่งสิ่งที่ต้องติดตั้งมีดังนี้

1.Adafriut SSD1306

2.Adafruit GFX

ซึ่งทั้งสองอันนี้เป็น Library ของ OLED display สามารถติดตั้งผ่าน Arduino IDE ได้เลย โดยเปิดโปรแกรมแล้วเข้าไปที่
Sketch > Include library > Manage library  search ชื่อ library แล้วกด install ได้เลย

3.SHT 1x – master  เป็น library ของ temperature sensor

Usage

OLLED สามารถเชื่อมต่อได้ทั้งในรูปแบบ I2C และ SPI 


#define OLED_MOSI   9
#define OLED_CLK   10
#define OLED_DC    11
#define OLED_CS    12
#define OLED_RESET 13

Adafruit_SSD1306 display(OLED_MOSI, OLED_CLK, OLED_DC, OLED_RESET, OLED_CS);
