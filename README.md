# Sandesh-Gowda
 
// include the library code:
#include <LiquidCrystal.h>
#include<dht.h>
dht DHT;
#define DHT11_PIN 8

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup()
{
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("COLD WATER");
  }

void loop() {
  {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  int chk = DHT.read11(DHT11_PIN); 
  lcd.print("Temp in `c ="); 
  lcd.print(DHT.temperature,1);
  delay(2000); 

  // print the number of seconds since reset:
  lcd.print(millis() / 1000);
}
}  
