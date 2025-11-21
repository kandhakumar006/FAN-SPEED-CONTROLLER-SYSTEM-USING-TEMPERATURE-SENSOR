# EXP 1(A) FAN SPEED CONTROLLER SYSTEM USING TEMPERATURE SENSOR

# Aim:
```
	To measure the Temperature using DHT11/DHT22/TMP36  sensor with Arduino UNO Board/ESP-32 using Tinker CAD.
```

# Hardware / Software Tools required:
```
	PC/ Laptop with Internet connection
    Tinker CAD tool (Online)
	Arduino UNO Board/ESP-32
	Temperature Sensor (DHT11/DHT22/TMP36)
```

# Circuit Diagram:
<img width="1361" height="739" alt="image" src="https://github.com/user-attachments/assets/c3c73531-e733-4f02-8957-238e161e192a" />

# Procedure 
Step 1: Set Up the Tinkercad Environment
1.	Log in to Tinkercad: Open Tinkercad in your web browser and log in to your account.
2.	Create a New Circuit: In the Tinkercad dashboard, click on "Circuits" and then select "Create New Circuit."
Step 2: Add Components to the Circuit
1.	Arduino Uno: Drag an Arduino Uno board from the components panel onto the workspace.
2.	TMP36 Sensor: Search for the TMP36 sensor in the components panel and drag it into the workspace.
3.	Breadboard: Drag a small breadboard to the workspace to help with wiring connections.
4.	Resistor (Optional): A resistor may not be necessary for this simple setup, but you can include it for more accurate readings.
5.	Wires: Use wires to connect the components.

Step 3: Connect the TMP36 Sensor to the Arduino
1.	TMP36 Pins:
o	Vout (Middle Pin): Connect this to an analog input pin on the Arduino (e.g., A0).
o	GND (Right Pin): Connect this pin to the ground (GND) on the Arduino.
o	Vs (Left Pin): Connect this to the 5V pin on the Arduino.
2.	Breadboard Wiring:
o	TMP36 Vout (Middle Pin) to Arduino A0: Use a wire to connect the middle pin (Vout) of the TMP36 sensor to the A0 analog input pin on the Arduino.
o	TMP36 GND (Right Pin) to Breadboard GND Rail: Connect the GND pin of the TMP36 sensor to the ground rail of the breadboard.
o	TMP36 Vs (Left Pin) to Breadboard 5V Rail: Connect the Vs pin of the TMP36 sensor to the 5V rail of the breadboard.
o	Arduino GND to Breadboard GND Rail: Connect a wire from the Arduino GND pin to the ground rail on the breadboard.
o	Arduino 5V to Breadboard 5V Rail: Connect a wire from the Arduino 5V pin to the power rail on the breadboard.
Step 4: Write the Arduino Code
1.	Code Editor: Click on the "Code" button at the top of the Tinkercad workspace to open the code editor.
2.	Set the Coding Mode: Ensure the editor is in "Text" mode to write your code in C/C++.
3.	Enter the Code: Write the following code to read the temperature from the TMP36 sensor
Step 5: Simulate the Circuit
1.	Start Simulation: Click the "Start Simulation" button at the top of the workspace to run the circuit and code.
2.	Monitor Output: Open the serial monitor by clicking the "Serial Monitor" button to view the temperature readings in both Celsius and Fahrenheit.
Step 6: Troubleshoot and Refine
1.	Check Connections: Ensure that all connections are made correctly on the breadboard and the Arduino.
2.	Adjust Code: If needed, tweak the code to improve accuracy or change the format of the output.
Step 7: Save Your Work
1.	Stop Simulation: Click "Stop Simulation" to end the simulation.
2.	Save the Circuit: Click "Save" to keep your circuit design and code for future use.


# Program

```
#include <LiquidCrystal.h>
LiquidCrystal lcd(9,8,7,6,5,4);
float temp; 
int tempPin= A0;
#define fan 3
void setup()
{ lcd.begin(16,2); 
 pinMode(fan,OUTPUT);
/*lcd.setCursor(0,0);
lcd.print("Hello friends!!");
 delay(1000);
lcd.clear();
 lcd.setCursor(2,0);
lcd.print("Our First ");
 delay(1000);

 lcd.setCursor(2,1);
lcd.print("ELC Project!!");
 delay(2000);
lcd.clear();
 lcd.setCursor(0,0); 
 lcd.print("Temperature Based"); 
 delay(1000); 
  
 lcd.setCursor(0,1); 
 lcd.print("FanSpeed Control");
 delay(2000); 
 lcd.clear();
 lcd.setCursor(2,0); 
 lcd.print("Group");
 delay(1000); 
 
 lcd.setCursor(2,1); 
 lcd.print("Memebers:");
 delay(2000); 
 lcd.clear();
 lcd.setCursor(0,0); 
 lcd.print("Ruthwik Sai");
 delay(1000); 

 lcd.setCursor(0,1); 
 lcd.print("Mukthesh");
 delay(2000); 
 lcd.clear();*/
} 
void loop()
{ lcd.setCursor(3,0);
 lcd.print("Recording"); 
 lcd.setCursor(2,1); 
 lcd.print("Temperature"); 
 delay(3000);
lcd.clear(); 
 lcd.setCursor(0,2); 
 temp = analogRead (tempPin); 
 temp = (0.0048828125)*temp; 
temp = (temp - 0.5) * 100 ;
 lcd.setCursor(1,0); 
 lcd.print("Temprature in");
 lcd.setCursor(1,1); 
 lcd.print("Celsius=");
 lcd.setCursor(9,1); 
 lcd.print(temp); 
 delay(3000); 
 lcd.clear();
if (temp<20)
{ analogWrite(fan,0);
lcd.print("Fan off"); delay(2000);
lcd.clear();
}
if (temp>20 && temp<=40)
{ analogWrite(fan,50);
lcd.print("Fan speed : 20% "); delay(2000);
lcd.clear();
} if (temp>40 && temp<=60)
{ analogWrite(fan,100);
lcd.print("Fan speed : 40% "); delay(2000);
lcd.clear();
} if (temp>60 && temp<=70)
{ analogWrite(fan,150);
lcd.print("Fan speed : 60% "); delay(2000);
lcd.clear();
} if (temp>70 && temp<=80)
{ analogWrite(fan,200);
lcd.print("Fan speed : 80% "); delay(2000);
lcd.clear();
} if (temp>80)
{ analogWrite(fan,255);
lcd.print("Fan speed : 100% "); delay(2000);
lcd.clear();
}
}

```
# Output :


https://github.com/user-attachments/assets/9d9011a1-4fc4-4989-9f7b-5fdd1a173b9a
# Result
FAN SPEED CONTROLLER SYSTEM USING TEMPERATURE SENSOR USING TINKERCAD EXECUTED SUCCESSFULLY.
