# Installation 
ก่อนอื่นต้องติดตั้ง library ให้กับ Arduino ก่อน ซึ่งสิ่งที่ต้องติดตั้งมีดังนี้

1. Adafriut SSD 1306

2.Adafriut GFX

ซึ่งทั้งสองอันนี้เป็น Library ของ OLED display สามารถติดตั้งผ่าน Arduino IDE ได้เลย โดยเปิดโปรแกรมแล้วเข้าไปที่
Sketch > Include library > Manage library  search ชื่อ library แล้วกด install ได้เลย

3. SHT 1x – master   เป็น library ของ temperature sensor

# Usage

OLLED สามารถเชื่อมต่อได้ทั้งในรูปแบบ I2C และ SPI  ซึ่งเราสามารถกำหนด PIN สำหรับเชื่อมต่อได้

      #define OLED_MOSI   9
      #define OLED_CLK   10
      #define OLED_DC    11
      #define OLED_CS    12
      #define OLED_RESET 13
      Adafruit_SSD1306 display(OLED_MOSI, OLED_CLK, OLED_DC, OLED_RESET, OLED_CS);

เช่นเดียวกันกับ SHT11 ที่เป็น I2C เราสามารถกำหนด SCL และ SDA ได้เช่นกัน

        #include <SHT1x.h>
        #define dataPin 10
        #define clockPin 11
        SHT1x sht1x(dataPin, clockPin);


# ReadTemperature and Humidity

SHT11 สามารถอ่านค่าอุณหภูมิแแล้วreturnออกมาเป็นค่าfloatได้ 

         float tempC = sht1x.readTemperatureC();`
         float humidity = sht1x.readHumidity);`

# Display Value on OLED

เราสามารถนำค่าจากsensorมาแสดงบนจอOLEDได้

          void readValue(void) {

         temp_c = sht1x.readTemperatureC();
         humidity = sht1x.readHumidity();
 
         display.setTextSize(2); // กำหนดขนาดตัวอักษร
         display.setTextColor(WHITE); // กำหนดสีตัวอักษร
  
         display.setCursor(0,0); // กำหนดตำแหน่งที่จะแสดง (x,y)
         display.clearDisplay();
         display.println(F("Temp")); // ข้อความที่จะแสดง
         display.display();
         display.setCursor(50,0);
         display.println(temp_c);
         display.setCursor(120,0);
         display.println("C");
   














