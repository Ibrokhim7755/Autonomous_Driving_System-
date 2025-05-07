# Autonomous_Driving_System

Autonomous driving system (ya'ni, o'z-o'zini boshqaruvchi avtomobil tizimi) — bu mashinaning inson aralashuvisiz harakatlanishini ta'minlaydigan murakkab texnologik tizimdir. U bir nechta asosiy komponentlar orqali ishlaydi:

🧠 **1. Sensorlar (Sezgir qurilmalar)**
Mashina atrof-muhitni "ko'rish" uchun turli sensorlardan foydalanadi:
- **Kameralar** – yo'l belgilari, chiziqlar, piyodalar va boshqa transport vositalarini aniqlaydi.

- **LiDAR** (Light Detection and Ranging) – lazer orqali atrofdagi obyektlarning 3D xaritasini tuzadi.

- **Radar** – uzoq masofadagi harakatlanuvchi obyektlarni aniqlaydi.

- **Ultrasonik sensorlar** – yaqin atrofdagi to‘siqlarni, masalan, to‘xtashda boshqa mashinalarni aniqlashda yordam beradi.

- **GPS va IMU (Inertial Measurement Unit)** – aniq joylashuvni aniqlaydi va harakat yo'nalishini kuzatib boradi.

 🧠 **2. Perception (Idrok qilish)**
Sensorlardan kelgan ma'lumotlar asosida mashina:

- Yo‘l chiziqlarini,

- Transport vositalarini,

- Piyodalarni,

- Yo‘l belgilarini va svetoforlarni aniqlaydi.

Bu bosqichda kompyuter ko‘rish (computer vision) va sun’iy intellekt (AI) ishlatiladi.

**🧠 3. Localization (Aniq joylashuvni aniqlash)**
Mashina o‘zini xaritada aniq qaerda joylashganini aniqlaydi. GPS + sensorlar yordamida 10–20 sm aniqlikda pozitsiya topiladi.

**🧠 4. Planning (Rejalashtirish)**
Mashina:

Qayerdan qayerga borishni,

Harakat yo‘nalishini,

Qanday qilib xavfsiz burilishni yoki to‘xtashni rejalashtiradi.

Bu bosqichda algoritmlar yo‘l harakati qoidalariga mos ravishda qarorlar qabul qiladi.

**🧠 5. Control (Boshqaruv)**
Oxirgi bosqichda mashina:

Rulni buradi,

Tezlikni oshiradi yoki kamaytiradi,

Tormoz bosadi.

Bularning barchasi avtomatik ravishda, inson yordamisiz amalga oshiriladi.



