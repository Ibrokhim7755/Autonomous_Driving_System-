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


# 🔍 LiDAR qanday ishlaydi?
1. Lazer nurlari yuboriladi
LiDAR qurilmasi har soniyada minglab lazer impulslarini atrofga uzatadi. Bu lazer nurlari obyektlarga uriladi va qaytadi.

2. Refleksiya (qaytgan nurlar) o‘lchanadi
Lazer nuri obyektga tekkanidan so‘ng, u orqaga — LiDAR sensoriga qaytadi. Sensor shu nurning borib-kelish vaqtini (time-of-flight) o‘lchaydi.

3. Masofa hisoblanadi
Borib-kelish vaqti asosida quyidagicha masofa hisoblanadi:

***Masofa = nurning borib-kelish vaqti * yorug’lik tezligi / 2***
​
 
(chunki nurlar borib va qaytib keladi — shuning uchun 2 ga bo‘linadi)

4. 3D nuqta buluti (point cloud) yaratiladi
Har bir lazer nuri obyektning aniq joylashgan nuqtasini ifodalaydi. Minglab nuqtalar yig‘ilib, atrof-muhitning 3D modeli hosil bo‘ladi. Bu "nuqta buluti" (point cloud) deb ataladi.

5. Real vaqtda yangilanadi
LiDAR aylanadigan holatda ishlasa, u har sekundda 360° atrof-muhitni skaner qiladi va real vaqtda 3D xaritani doimiy yangilab turadi.

# 📌 LiDAR’ning afzalliklari:
Juda aniq va to‘liq 3D tasvir beradi

Kechasi ham ishlaydi (chunki o‘z nurlari bor)

Obyektlarning aniq o‘lchamini va joylashuvini aniqlaydi

# ⚠️ Kamchiliklari:
Qimmat

Yomg‘ir, qor yoki changli ob-havo aniqlikka ta'sir qilishi mumkin

# 🔗 LiDAR va KNN o‘rtasidagi bog‘liqlik
**🟢 1. LiDAR ma’lumotlari – “Point Cloud”**
LiDAR atrofdagi obyektlar haqida minglab 3D nuqtalar (point cloud) shaklida ma’lumot to‘playdi. Har bir nuqta x, y, z koordinatalariga ega bo‘ladi.

🟢 2. Bu nuqtalarni guruhlash yoki tasniflash kerak
Masalan:

Bu nuqtalar avtomobilga, piyodaga, yoki yo‘l chetiga tegishli ekanini aniqlash.

Ya’ni, har bir nuqtani toifalash (classification) yoki obyektlarga ajratish (clustering).

🟢 3. KNN bu yerda ishlatiladi
KNN (K-Eng yaqin qo‘shni algoritmi) yordamida:

Har bir nuqtaga eng yaqin K ta qo‘shni nuqta topiladi.

Ularning toifasiga qarab, markaziy nuqtaning qaysi obyektga tegishli ekanini aniqlash mumkin.

Masalan: Agar nuqtaning atrofidagi 5 ta qo‘shni nuqtaning 4 tasi "piyoda" bo‘lsa, u nuqta ham "piyoda" deb belgilanishi mumkin.

📦 KNN LiDAR ma’lumotlarida ishlatiladigan joylar:
Obyektlarni tasniflash (classification)

Segmentatsiya (nuqtalarni guruhlarga ajratish)

Anomaliyalarni aniqlash (masalan, kutilmagan nuqtalar)

3D harita yaratishda filtratsiya (keraksiz nuqtalarni olib tashlash)

# 🧠 Qisqacha:
LiDAR — ma’lumot to‘playdi,
KNN — o‘sha ma’lumot asosida tahlil yoki tasniflash qiladi.

# ☁️ 1. Point Cloud (Nuqta buluti)
Ta’rif:
Point cloud — bu 3D makondagi nuqtalar to‘plami, har bir nuqta odatda (x, y, z) koordinatalariga ega. Bu nuqtalar LiDAR, stereo kameralar yoki boshqa 3D skanerlar yordamida yaratiladi.

Ma’no jihatidan:

Har bir nuqta obyektning tashqi yuzasidagi bir nuqtani ifodalaydi.

Minglab nuqtalar yig‘ilib, real dunyoning 3D modelini hosil qiladi.

Rang (RGB), zichlik, reflektivlik kabi qo‘shimcha atributlar ham bo‘lishi mumkin.

**📌 Qo‘llaniladi:**

3D kartografiya

Obyekt tanish

Robotika va avtonom haydash

