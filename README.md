# arduinofirealarm
an arduino based fire alarm system

int Buzzer = 13; // Use buzzer for alert 
int FlamePin = 2; // This is for input pin
int Flame = HIGH; // HIGH when FLAME Exposed
int Hot = 8;// To detect flame 
int Cold = 9;// To display that it is safe

void setup() {
 pinMode(Buzzer, OUTPUT);
 pinMode(FlamePin, INPUT);
 Serial.begin(9600);
}
 
void loop() {
 Flame = digitalRead(FlamePin);
 Serial.println(Flame);
 if (Flame== HIGH)
 {
 Serial.println("HIGH FLAME");
 digitalWrite(Buzzer, LOW);
 digitalWrite(Cold, HIGH);
 digitalWrite(Hot, LOW);
 }
 else
 {
 Serial.println("NO FLAME");
 digitalWrite(Buzzer, HIGH);
 digitalWrite(Hot, HIGH);
 digitalWrite(Cold, LOW);
 }
}
