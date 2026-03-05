# 📘 HTML Darsi: Formalar (Forms) va Input turlari

Veb-saytlarda foydalanuvchi bilan muloqot qilish, ma'lumotlarni qabul qilish (ro'yxatdan o'tish, qidiruv, fikr qoldirish) uchun **Formalar** ishlatiladi.

---

## 1. <form> tegi va asosiy atributlar

Hamma forma elementlari `<form>` tegi ichiga yoziladi.

* **action**: Ma'lumotlar yuborilishi kerak bo'lgan server manzili (URL).
* **method**: Ma'lumotni yuborish usuli:
    * `GET`: Ma'lumotlarni manzil satrida ko'rinadigan qilib yuboradi.
    * `POST`: Ma'lumotlarni yashirin va xavfsiz yuboradi (parollar uchun majburiy).

---

## 2. <label> va "for" atributi

`<label>` — foydalanuvchiga input nima ekanligini tushuntiruvchi matn.
* **for**: Bu atribut inputning **id**si bilan bir xil bo'lishi shart.
* **Foydasi**: Label ustiga bosilganda kursiv avtomatik ravishda tegishli inputga o'tadi.

---

## 3. `<input>` va uning turlari (Type)

`<input>` tegi yopiluvchi juftiga ega emas. Uning vazifasi `type` atributiga qarab o'zgaradi.

### 📝 Matnli maydonlar:
1.  **type="text"**: Oddiy matn (ism, familiya) kiritish uchun.
2.  **type="password"**: Parol kiritish uchun (belgilar nuqta yoki yulduzcha bo'lib ko'rinadi).
3.  **type="email"**: Faqat email formatidagi matnni qabul qiladi (`@` belgisi bo'lishi shart).
4.  **type="date"**: Sana tanlash uchun maxsus kalendarni ochadi.

### 🔘 Tanlov elementlari:
5.  **type="checkbox"**: "Ha" yoki "Yo'q" varianti. Bir vaqtning o'zida bir nechtasini tanlash mumkin.
6.  **type="radio"**: Bir nechta variantdan faqat **bittasini** tanlash uchun.
    * **Muhim**: Bir nechta radio tugmalar bitta guruhga tegishli bo'lishi uchun ularning `name` atributi bir xil bo'lishi kerak.
    * **value**: Serverga aynan qaysi variant tanlangani haqidagi qiymatni yuboradi.

### 📁 Fayl yuklash:
7.  **type="file"**: Kompyuterdan fayl (rasm, dokument) yuklash imkonini beradi.



---

## 4. Button (Tugma) yaratish

Formani yakunlash va yuborish uchun tugma kerak:
* `<button type="submit">` — Ma'lumotlarni serverga yuboradi.

---

## 🏗 To'liq kod namunasi

Ushbu kodni brauzerda tekshirib ko'ring:

```html
<form action="/login-server" method="POST">
    <div>
        <label for="username">Username:</label>
        <input type="text" name="user_name" id="username" placeholder="Ismingizni yozing">
    </div>

    <br>

    <div>
        <label for="parol">Parol:</label>
        <input type="password" name="user_password" id="parol">
    </div>

    <br>

    <div>
        <label for="email">Email:</label>
        <input type="email" id="email" name="user_mail">
        
        <label for="tugulgan_kun">Tug'ilgan sana:</label>
        <input type="date" id="tugulgan_kun" name="birth_date">
    </div>

    <br>

    <div>
        <p>Jinsingizni tanlang:</p>
        <input type="radio" id="erkak" name="gender" value="male">
        <label for="erkak">Erkak</label>

        <input type="radio" id="ayol" name="gender" value="female">
        <label for="ayol">Ayol</label>
    </div>

    <br>

    <div>
        <input type="checkbox" id="news" name="subscribe">
        <label for="news">Yangiliklarga obuna bo'lish</label>
        
        <br><br>
        
        <label for="rasm">Profil uchun rasm yuklang:</label>
        <input type="file" id="rasm" name="user_photo">
    </div>

    <br>

    <button type="submit">Ro'yxatdan o'tish</button>
</form>