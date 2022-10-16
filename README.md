
#include <BluetoothSerial.h>

BluetoothSerial SerialBT;

int kontak = 15;
int stater = 12;
int lampu = 14;
int klakson = 27;
int ad = 13;

void setup() {
  SerialBT.begin("Motor 22");
  Serial.begin(115200);
  
  pinMode(kontak,OUTPUT);
  digitalWrite(kontak,HIGH); 

   pinMode(stater,OUTPUT);
  digitalWrite(stater,HIGH); 

   pinMode(lampu,OUTPUT);
  digitalWrite(lampu,HIGH); 

   pinMode(klakson,OUTPUT);
  digitalWrite(klakson,HIGH); 
    
    pinMode(ad,OUTPUT);
  digitalWrite(ad,HIGH); 
  
  
}

void loop() 
{   
  
  if (SerialBT.available()) { 
    int x = SerialBT.read(); 
    Serial.write(x); 
   
    if (char(x) == '0') {
      digitalWrite(kontak,LOW);
      
    }   
    
    if (char(x) == '1') { 
      digitalWrite(kontak,HIGH);
      
    }

    if (char(x) == '2') {
      digitalWrite(stater,LOW);
            delay(500);
      digitalWrite(stater,HIGH);
            
     
    }   
    
    if (char(x) == '3') { 
      digitalWrite(stater,HIGH);
      
    }
    if (char(x) == '4') {
      digitalWrite(lampu,LOW);
      
    }   
    
    if (char(x) == '5') { 
      digitalWrite(lampu,HIGH);
      
    }
    if (char(x) == '6') {
      digitalWrite(klakson,LOW);
     
    }   
    
    if (char(x) == '7') { 
      digitalWrite(klakson,HIGH);
      
    }
        
     if (char(x) == 'a') { 
      digitalWrite(ad,LOW);
      
    }
    
    if (char(x) == 'b') { 
      digitalWrite(ad,HIGH);
      
    }
    
    if (char(x) == 'c') { 
      digitalWrite(klakson,LOW);
            delay(100);
      digitalWrite(klakson,HIGH);
    }
}

}
