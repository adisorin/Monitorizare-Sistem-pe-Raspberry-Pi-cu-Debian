# Monitorizare-Sistem-pe-Raspberry-Pi-cu-Debian
Monitorizare Sistem pe Raspberry Pi cu Debian

<img width="552" height="509" alt="image" src="https://github.com/user-attachments/assets/1e75af9d-627c-4c96-b82a-fd3dac777570" />

Prezentare: Monitorizare Sistem pe Raspberry Pi cu Debian

1️⃣ Introducere
Acest proiect reprezintă o aplicație grafică de monitorizare în timp real a sistemului pentru Raspberry Pi care rulează Debian.
Aplicația afișează:
Utilizare CPU
Temperatură CPU
Utilizare RAM
Utilizare SSD
Trafic de rețea (Download / Upload)
Top procese după CPU și RAM
Grafic istoric CPU
Ceasuri analogice pentru fiecare parametru
Este o soluție ideală pentru:
Proiecte IoT
Servere locale pe Raspberry Pi
Sisteme embedded
Monitorizare pentru laborator sau prezentare educațională

2️⃣ Tehnologii utilizate
Aplicația este scrisă în Python și folosește următoarele biblioteci:
🔹 psutil

Colectează informații despre:
CPU
RAM
Disk
Rețea
Temperatură

Procese active:
🔹 customtkinter
Creează interfața grafică modernă (dark mode)
Oferă un design mai atractiv față de Tkinter standard
🔹 matplotlib
Generează graficul dinamic al utilizării CPU
🔹 threading
Rulează colectarea datelor în fundal fără să blocheze interfața

3️⃣ Arhitectura aplicației
Aplicația este structurată în mai multe componente:
🔸 1. Inițializare UI
Setare mod dark
Creare fereastră principală
Definire fonturi
Creare frame principal
🔸 2. Funcții principale
✔ format_bytes()

Transformă valori în bytes în:
KB
MB
GB
TB
✔ get_top_processes()
Colectează toate procesele active

Selectează:
Top 5 CPU
Top 5 RAM
✔ draw_analog()

Desenează un indicator analog pentru:
CPU
RAM
SSD
NET
Temperatură

Include:
Cerc exterior
Gradații 0–100
Indicator roșu
Label descriptiv
✔ update_stats() (Thread principal)

Rulează la fiecare 2 secunde:
Citește valorile sistemului
Calculează traficul de rețea
Citește temperatura CPU
Determină procesele dominante
Trimite datele către interfață
✔ update_ui()

Actualizează:
Label-uri text
Grafic CPU
Ceasuri analogice

4️⃣ Ce afișează aplicația
🖥️ CPU
Procent utilizare
Temperatură
Grafic istoric (ultimele 30 valori)

💾 RAM
Memorie utilizată / total

💽 SSD
Spațiu utilizat / total

🌐 Rețea
Download / Upload în timp real

🔥 Temperatură
Indicator analog separat

📊 Top Procese
Aplicații cu cel mai mare consum CPU
Aplicații cu cel mai mare consum RAM

5️⃣ Avantajele soluției pe Raspberry Pi
✔ Consum redus de resurse
✔ Funcționează stabil pe Debian
✔ Interfață modernă

6️⃣ Flux de execuție
Pornire aplicație
Lansare thread monitorizare
Colectare date la 2 secunde
Actualizare UI prin app.after()
Redesenare grafic + ceasuri

7️⃣ Posibile îmbunătățiri
Salvare istoric CPU în fișier
Alertă temperatură mare
Export date CSV
Interfață touchscreen
Integrare cu web dashboard
Monitorizare GPU (unde este disponibil)

8️⃣ Concluzie
Această aplicație transformă un Raspberry Pi cu Debian într-un sistem complet de monitorizare în timp real, cu interfață grafică modernă și indicatori analogici.
