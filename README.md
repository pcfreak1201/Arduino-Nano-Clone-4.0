# Arduino-Nano-Clone-4.0
## Arduino Nano Klon 4.0 auf Basis eines ATMega4808

### Wo geht der Weg hin (wenn wir wieder weiter gehen können)?

![Entwicklung](./images/ClassicModern.png)

Es gibt für mich als "Bastler" drei große Bereiche, für die ich Microcontroller einsetze:
1. "Mal eben"-Projekte die etwas einlsen, ausgeben oder steuern sollen. Meist mit **Arduino-Nano oder Mini** -- wenn es kleiner werden soll auch direkt ein **ATTiny** auf einem Breakout-Board
2. Komplexere Steuerungen mit etwas mehr Rechenpower und Computer-Anbindung (USB): **RP2040**
3. Netzwerk (WLAN) Anwendungen die etwas im Internet machen sollen: **ESP32**

Bei 2. und 3. macht eine Eigenentwicklung keinen Sinn, weil es genug Development-Boards auf dem Markt gibt. Doch gerade die beliebten Arduino-Boards der 1. Generation sind im Moment entweder schwer zu bekommen, oder extrem teuer (Klone liegen bei 8-12EUR).
Außerdem war nie ein Freund von Quarzen. Ich liebe interne Oszillatoren. Natürlich sind sie nicht sehr genau ... doch viele Boards verwenden billge Resonatoren statt Quarze - die sind auch nicht viel genauer.

Vorlage sind für mich hier zunächst das **ATMEGA4808 megaAVR Mini Dev. Board, Arduino Compatible**

(https://www.electrodragon.com/product/atmega4808-megaavr-mini-dev-board-arduino-compatible/)
![TopView](https://s5.electrodragon.com/wp-content/uploads/2020/11/ATMEGA4808-megaAVR-Mini-Dev.-Board-Arduino-Compatible-01.jpg)

Das dürfte die "Kaufvariante" der nächsten Generation sein. Bereits auf den MegaCoreX ausgelegt und kompatibel, günstig und kompakt.

Und da ist das **ATmega4808 Development Board** von [#wagiminator] Stefan Wagner 

(https://github.com/pcfreak1201/atmega4808/tree/master/ATmega4808_DevBoard)

![PinOut](https://github.com/wagiminator/AVR-Development-Boards/raw/master/ATmega4808_DevBoard/ATmega4808_DevBoard_pinout.png)

Welches mir als Inspiration für mein Board diente.

![Arduino-Nano-Clone-4.0](./images/m4808.png)

Da ich keinen Bedarf für einen 32kHz Quarz habe, habe ich diesen weggelassen. Da ich eigentlich keinen Upload per Bootloader vorhabe, sondern direkt per UPDI, habe ich ebenfalls den CH340N verwendet, der zwar ein RTS-Signal besitzt, aber kein DTR. Das hat mir unter Linux bisher immer Probleme gemacht, wenn es um den Upload per Bootloader ging. Aber die serielle Kommunikation funktioniert einwandfrei.
