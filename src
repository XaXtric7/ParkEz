#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <Servo.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);   
Servo myservo;

int IR1 = 2;
int IR2 = 3;

int Slot = 4;           // Total number of parking Slots
int flag1 = 0;
int flag2 = 0;

void setup() {
    Serial.begin(9600); 

    lcd.init(); // Initialize the LCD
    lcd.backlight(); // Turn on the backlight

    pinMode(IR1, INPUT);
    pinMode(IR2, INPUT);

    myservo.attach(4);
    myservo.write(100);

    lcd.setCursor(0, 0);
    lcd.print("     ARDUINO    ");
    lcd.setCursor(0, 1);
    lcd.print(" PARKING SYSTEM ");
    delay(2000);
    lcd.clear();  
}

void loop() { 
    if(digitalRead(IR1) == LOW && flag1 == 0) {
        if(Slot > 0) {
            flag1 = 1;
            if(flag2 == 0) {
                myservo.write(0);
                Slot -= 1; // Decrease slot count
            }
        } else {
            lcd.setCursor(0, 0);
            lcd.print("    SORRY :(    ");  
            lcd.setCursor(0, 1);
            lcd.print("  Parking Full  "); 
            delay(3000);
            lcd.clear(); 
        }
    }

    if(digitalRead(IR2) == LOW && flag2 == 0) {
        flag2 = 1;
        if(flag1 == 0) {
            myservo.write(0);
            Slot += 1; // Increase slot count
            if (Slot > 4) Slot = 4; // Ensure Slot does not exceed max
        }
    }

    if(flag1 == 1 && flag2 == 1) {
        delay(1000);
        myservo.write(100);
        flag1 = 0;
        flag2 = 0;
    }

    lcd.setCursor(0, 0);
    lcd.print("    WELCOME!    ");
    lcd.setCursor(0, 1);
    lcd.print("Slot Left: ");
    lcd.print(Slot);
    lcd.print("  "); // Clear extra characters if Slot is < 2 digits
}
