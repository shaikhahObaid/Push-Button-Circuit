# Push-Button-Circuit
Push button is one of the forms of the momentary switch, as it activates its work when pressed, while it returns to its basic state when the finger is lifted from it. (such as a doorbell that rings only while pressing it), its electronic symbol and shape are in most cases as in the following image:

![الضاغط مفصل ](https://github.com/shaikhahObaid/Push-Button-Circuit/assets/111530370/a1eb0cd1-4ace-4999-a85c-609f8fe638f9) 
![الضاغط عند الضغط](https://github.com/shaikhahObaid/Push-Button-Circuit/assets/111530370/4fc7ed38-e744-407a-a6c1-86ebf36fb133)


## Practical example - controlling the lighting of a two-light source via a push-button switch
 Explanation of circuit operation
Each time the key is pressed, the state of the light source diode changes, that is, if the light source diode lights up and the key is pressed, the light source diode stops working, and with a new press on the key, the diode will return to work, and so on.


## Components list
 ![العناصر](https://github.com/shaikhahObaid/Push-Button-Circuit/assets/111530370/f17b7b11-2b0e-4e85-b84e-d5036dd179c2)

## Circuit view and simulation
![الدائره ](https://github.com/shaikhahObaid/Push-Button-Circuit/assets/111530370/bb921c80-e2ce-47ee-b990-36590f96e514) 


https://www.tinkercad.com/things/dTmNwqnntIr-super-blad/editel?sharecode=MJY9MVMjCeogs5ldPSVIc3MgzmiFPMditFL3y2P5Tjs 


## The code 
int pin_button  = 2;    // Button pin


int pin_led     = 3;    // LED pin 

bool button_status;     // Save button status


bool led_state  = 0;    // Save led state 

void setup() 

{

  pinMode(pin_button, INPUT);
  
  pinMode(pin_led, OUTPUT);
  
}

void loop() 

{

  // Read current button status
  
  button_status = digitalRead(pin_button);

  // Check if button has been pressed
  
  if (button_status == 0) 
  
  {
    // Remove debounce effect by time-delay
    
    delay(150);
   
    // Check button again
    
    if (button_status == 0)
    
    {
      // Reverse the state of boolean variable
      
      led_state = !led_state;
    }
    
  }
 
  // Toggle-LED according to current value of variable "led_state" (1 : on, 0 : off)
  
  digitalWrite(pin_led, led_state );
  
}
