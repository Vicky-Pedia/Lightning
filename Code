#include <Adafruit_NeoPixel.h>

#define PIN 6        
#define NUM_LEDS 60  

Adafruit_NeoPixel strip = Adafruit_NeoPixel(NUM_LEDS, PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  strip.begin();
  strip.show();
}

void loop() {
  lightningStrike(255, 255, 255, 0, 0, 255, 5, 50, 5);
  delay(random(5000, 10000));
}

void lightningStrike(uint8_t whiteR, uint8_t whiteG, uint8_t whiteB, uint8_t blueR, uint8_t blueG, uint8_t blueB, int flashes, int delayBetweenFlashes, int flickerIntensity) {
  for (int i = 0; i < flashes; i++) {
    int brightness = random(150, 255);
    setAll(whiteR * brightness / 255, whiteG * brightness / 255, whiteB * brightness / 255);
    strip.show();
    delay(random(50, delayBetweenFlashes));

    brightness = random(100, 200);
    setAll(blueR * brightness / 255, blueG * brightness / 255, blueB * brightness / 255);
    strip.show();
    delay(random(50, flickerIntensity));
    
    setAll(0, 0, 0);
    strip.show();
    delay(random(20, flickerIntensity));
  }
}

void setAll(uint8_t r, uint8_t g, uint8_t b) {
  for (int i = 0; i < strip.numPixels(); i++) {
    strip.setPixelColor(i, strip.Color(r, g, b));
  }
}
