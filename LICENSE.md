//******MUHAMMED ALİ ÖZEN******

#include <LiquidCrystal.h> //lcd ekran kütüphanesi
LiquidCrystal lcd (12,11,5,4,3,2); // lcd bağlantı pinleri

int solust = 14;
int solorta = 15;
int solalt = 16;
int orta = 7;
int sagust = 17;
int sagorta = 18;
int sagalt = 19;

int buton = 9; //buton baglantı pini
int butondurum; // butonun basılıp basılmama durumu

long zar; //random (rastgele) olan sayıların degerini atamak 
int time = 2000; //zarın sonucunu göstermek için 
int show = 100; // butona  basıldıgında yapılcak olan show

void setup ()
{
  lcd.begin(16,2);
  pinMode (solust, OUTPUT);
  pinMode (solorta, OUTPUT);
  pinMode (solalt, OUTPUT);
  pinMode (orta, OUTPUT);
  pinMode (sagust, OUTPUT);
  pinMode (sagorta, OUTPUT);
  pinMode (sagalt, OUTPUT);
  pinMode (buton, INPUT);
  randomSeed(analogRead(0));
}

void loop()
{
  butondurum = digitalRead(buton);
  if (butondurum == HIGH){
    //show
      digitalWrite (solust, HIGH);
      delay(show);
      digitalWrite (solorta, HIGH);
      delay(show);
      digitalWrite (solalt, HIGH);
      delay(show);
      digitalWrite (orta, HIGH);
      delay(show);
      digitalWrite (sagust, HIGH);
      delay(show);
      digitalWrite (sagorta, HIGH);
      delay(show);
      digitalWrite (sagalt, HIGH);
      delay(show);
      digitalWrite (solust, LOW);
      digitalWrite (solorta, LOW);
      digitalWrite (solalt, LOW);
      digitalWrite (orta, LOW);
      digitalWrite (sagust, LOW);
      digitalWrite (sagorta, LOW);
      digitalWrite (sagalt, LOW);
    
    zar = random(1, 7);
  lcd.print("cikan sonuc  = ");
    lcd.println(zar);
    lcd.clear();
      lcd.print("cikan sonuc  = ");
    lcd.println(zar);
 
    if (zar == 1){
      digitalWrite (orta, HIGH);
      delay (time);
    }
    if (zar == 2){
      digitalWrite (solust, HIGH);
      digitalWrite (sagalt, HIGH);
      delay (time);
    }
    if (zar == 3){
      digitalWrite (solust, HIGH);
      digitalWrite (orta, HIGH);      
      digitalWrite (sagalt, HIGH);
      delay (time);
    }
    if (zar == 4){
      digitalWrite (solust, HIGH);
      digitalWrite (solalt, HIGH);
      digitalWrite (sagust, HIGH);
      digitalWrite (sagalt, HIGH);
      delay (time);
    }
    if (zar == 5){
      digitalWrite (solust, HIGH);
      digitalWrite (solalt, HIGH);
      digitalWrite (orta,   HIGH);
      digitalWrite (sagust, HIGH);
      digitalWrite (sagalt, HIGH);
      delay (time);
   }
   if (zar == 6){
      digitalWrite (solust, HIGH);
      digitalWrite (solorta, HIGH);
      digitalWrite (solalt, HIGH);
      digitalWrite (sagust, HIGH);
      digitalWrite (sagorta, HIGH);
      digitalWrite (sagalt, HIGH);
      delay (time);
   }
  }
      digitalWrite (solust, LOW);
      digitalWrite (solorta, LOW);
      digitalWrite (solalt, LOW);
      digitalWrite (orta, LOW);
      digitalWrite (sagust, LOW);
      digitalWrite (sagorta, LOW);
      digitalWrite (sagalt, LOW);
}
