
#include <LiquidCrystal.h>


LiquidCrystal lcd (12,11,5,4,3,2);
char vector [10];
String dato;
int contador=0;

void setup() {

  lcd.begin(16,2);
  Serial.begin(9600);
  
}


void loop() {
  if (Serial.available()>0)
  {
   
   dato=Serial.readString();
    dato.toCharArray(vector,dato.length());
   Serial.println(dato);
  }
  
  lcd.clear();
  
 for (contador=0;contador<dato.length();contador++)
 
  {
    lcd.setCursor(contador, 0);
    
    
    lcd.print(vector[contador]);
    
    delay(200);
    
  }
}
