# Arduino
int ledPin = 9;
boolean estadoLed = false;

void setup() {
   Serial.begin(9600);
   pinMode(ledPin, OUTPUT);
   digitalWrite(ledPin,estadoLed);
   pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  
   digitalWrite(LED_BUILTIN, HIGH);   // encender LED (HIGH es el nivel de voltaje)
   delay(2000);                       // esperar dos segundos
   digitalWrite(LED_BUILTIN, LOW);    // apagar LED reduciendo voltajee
   delay(1000);                       // esperar un segundo

   if (Serial.available()){
     char Letra = Serial.read();
            if (Letra== 'a'){         //Presionar letra a para enccender y apagar led
                  estadoLed= !estadoLed;
               }
             digitalWrite(ledPin,estadoLed);
            }
 }
