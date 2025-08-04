//#include 
int bulb = 13;    	            	 
int inputPir = 2;                   
int val = 0;                        
int hasilSensorLDR; 	
int sensorLDR = A0; 	
void setup() { 
  pinMode(bulb, OUTPUT);          
  pinMode(inputPir, INPUT);          
  pinMode(sensorLDR, INPUT);		
  Serial.begin(9600); 				
    
} 
void loop(){ 
  val = digitalRead(inputPir); 
  hasilSensorLDR = analogRead(sensorLDR);  
  if (hasilSensorLDR<600){ 			 	
	  if (val == HIGH) { 
    	digitalWrite(bulb, HIGH); 
   	 	delay(1000); 				
  } 
  else { 
      digitalWrite(bulb, LOW); 
      delay(300);   
  }  
} 
  else{ digitalWrite(bulb,LOW); 	
  Serial.println(hasilSensorLDR); 	
  delay(500); 	
      }
 }
