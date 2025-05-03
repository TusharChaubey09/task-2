#include <Wire.h>         // adds I2C library 
#include <BH1750.h>       // adds BH1750 library file 
#define BLYNK_PRINT Serial
#include <Blynk.h>
#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>
 
char auth[] = "Sunny251";       // You should get Auth Token in the Blynk App.
char ssid[] = "Oneplusnord2t";                       // Your WiFi credentials.
char pass[] = "15092001";
 
BH1750 lightMeter;
 
void setup()
{
  Wire.begin();
  Serial.begin(9600);
  Blynk.begin(auth, ssid, pass);
  lightMeter.begin();
 
}
void loop() 
{
Blynk.run();
  float lux = lightMeter.readLightLevel();
  Serial.print("Light Meter: ");
  Serial.print(lux);
  Serial.println(" lx");
  Blynk.virtualWrite(V2, lux);
  delay(1000);
} 
