#ESP32 3S BMS & Telemetry Node

Prosty, niezawodny system zarządzania pakietami Li-Po 3S oparty na mikrokontrolerze ESP32. Układ komunikuje się po magistrali SPI.

* **UVP / OVP (Under/Over-Voltage Protection):** Indywidualne monitorowanie napięcia każdej celi (domyślnie: min. 3.00 V, max. 4.20 V).
* **OCP (Over-Current Protection):** Ciągły pomiar poboru prądu pod obciążeniem (limit: 12.00 A).
* **OTP (Over-Temperature Protection):** Monitorowanie temperatury ogniw zapobiegające Thermal Runaway (limit: 50.0 °C).
* **Telemetria JSON:** Asynchroniczne wysyłanie ramek danych.

Specyfikacja Sprzętowa 

* **MCU:** ESP32-WROOM-32E (Moduł z Wi-Fi & Bluetooth, taktowanie do 240 MHz).
* **Zasilanie (Power Management):** Zintegrowana przetwornica Buck LM2596T-5 (obniżająca napięcie pakietu do 5V) oraz stabilizator LDO LD1086DT33TR (3.3V dla logiki). Wejście chronione przed odwrotną polaryzacją za pomocą P-MOSFETa.
* **Interfejs USB & Flash:** Złącze USB-C z zabezpieczeniem ESD (USBLC6-2SC6). Wbudowany konwerter USB-UART na układzie CH340C z obwodem Auto-Reset umożliwiającym płynne programowanie.
* **Pomiar Napięcia:** Indywidualny odczyt napięć na celach (V1+, V2+, V3+). Dzielniki rezystorowe załączane dynamicznie przez N-MOSFETy i separowane optoizolatorami (SFH617A), co całkowicie eliminuje problem samorozładowania pakietu.
* **Pomiar Prądu:** Pomiar na dedykowanym wzmacniaczu operacyjnym INA213 współpracującym z rezystorem bocznikowym (Shunt) 10 mΩ.
* **Pomiar Temperatury:** Dwutorowy układ pomiarowy: klasyczny termistor NTC oraz analogowy tor dla czujnika PT100 zrealizowany na układzie LM324.
* **Load Switch:** Sprzętowe odłączanie obciążenia (High-Side) realizowane za pomocą tranzystorów P-MOSFET IRF4905 sterowanych złączami optoizolowanymi.

##Struktura Repozytorium
* **`README.md`** - Główna dokumentacja projektu.
* **`/.gitignore`** - Reguły ignorowania plików tymczasowych (m m.in. KiCada i środowisk programistycznych).
* **`/Hardware`** - Pliki źródłowe projektu (schematy i projekt PCB) wykonane w programie KiCad.
* **`/Firmware`** - Kod źródłowy dla mikrokontrolera ESP32.
* **`/Docs`** - Dokumentacja dodatkowa (schematy w formacie PDF, rendery 3D).
