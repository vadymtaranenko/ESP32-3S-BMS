#ESP32 3S BMS & Telemetry Node

Prosty, niezawodny system zarządzania pakietami Li-Po 3S oparty na mikrokontrolerze ESP32. Układ komunikuje się po magistrali SPI.

* **UVP / OVP (Under/Over-Voltage Protection):** Indywidualne monitorowanie napięcia każdej celi (domyślnie: min. 3.00 V, max. 4.20 V).
* **OCP (Over-Current Protection):** Ciągły pomiar poboru prądu pod obciążeniem (limit: 12.00 A).
* **OTP (Over-Temperature Protection):** Monitorowanie temperatury ogniw zapobiegające Thermal Runaway (limit: 50.0 °C).
* **Telemetria JSON:** Asynchroniczne wysyłanie ramek danych (5 Hz) do komputera pokładowego (np. Raspberry Pi, Jetson, Pixhawk).

##Struktura Repozytorium
* **`README.md`** - Główna dokumentacja projektu.
* **`/.gitignore`** - Reguły ignorowania plików tymczasowych (m m.in. KiCada i środowisk programistycznych).
* **`/Hardware`** - Pliki źródłowe projektu (schematy i projekt PCB) wykonane w programie KiCad.
* **`/Firmware`** - Kod źródłowy dla mikrokontrolera ESP32.
* **`/Docs`** - Dokumentacja dodatkowa (schematy w formacie PDF, rendery 3D).
