# Task 1 – Controlling 5 Servo Motors with Arduino UNO  

##  Objective  
The objective of this task is to control **five servo motors** simultaneously using an **Arduino UNO**.  
- First, the servos will sweep together.  
- Then, they will all stop at **90°**.  

---

##  Components Used  
- Arduino UNO  
- 5 × Servo Motors   
- Breadboard  
- External 5V DC Power Supply (to power all servos)  
- Jumper Wires  

---

##  Circuit Connections  
- **Servo Signals** → Arduino pins **3, 5, 6, 9, 10**  
- **Servo VCC (Red)** → 5V (external supply)  
- **Servo GND (Brown/Black)** → GND (shared with Arduino GND)  
- **Arduino GND** → common ground with external supply  

---

##  Screenshots

![Simulation Screenshot](https://i.imgur.com/abcd123.png)
![Simulation Screenshot](https://i.imgur.com/abcd123.png)

---

##  Project Link
[ Open in Tinkercad](https://www.tinkercad.com/)




## Code  

```cpp
#include <Servo.h>

Servo servos[5];
int pins[5] = {3, 5, 6, 9, 10};

void setup() {
  for (int i = 0; i < 5; i++) {
    servos[i].attach(pins[i]);
  }
}

void loop() {
  for (int pos = 0; pos <= 180; pos += 5) {
    for (int i = 0; i < 5; i++) servos[i].write(pos);
    delay(20);
  }

  for (int pos = 180; pos >= 0; pos -= 5) {
    for (int i = 0; i < 5; i++) servos[i].write(pos);
    delay(20);
  }

  for (int i = 0; i < 5; i++) servos[i].write(90);

  while(true);
}

  while (true) {}    // Stop execution
}
