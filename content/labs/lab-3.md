## Тема, Мета, Місце розташування

**Тема:** "РОЗРОБКА ФУНКЦІОНАЛЬНОГО REST API. РЕЄСТРАЦІЯ ТА АВТОРИЗАЦІЯ КОРИСТУВАЧІВ. ВАЛІДАЦІЯ ДАНИХ І ОБРОБКА ПОМИЛОК."

**Мета:**
- вивчення принципів побудови REST API;
- набуття практичних навичок розробки серверного застосунку з використанням платформи Node.js і фреймворку Express;
- реалізувати механізми реєстрації та авторизації користувачів;
- забезпечити валідацію вхідних даних;
- забезпечити обробку помилок;
- організувати захищений доступ до ресурсів із використанням JWT-токенів і системи ролей
користувачів.

**Місце розташування:**
- Репозиторій звітного HTML-документа: (https://github.com/klynxlx/IS-32_appRECORD-LinnykKatya-FIOT-2026)
- Звітний HTML-документ (Жива сторінка): (https://klynxlx.github.io/IS-32_appRECORD-LinnykKatya-FIOT-2026/)
- Репозиторій власного веб-застосунку: (https://github.com/klynxlx/IS-32_appWEB-LinnykKatya-FIOT-2025-)
- Власний веб-застосунок (Жива сторінка): (https://klynxlx.github.io/IS-32_appWEB-LinnykKatya-FIOT-2025-/)

## Реалізувати реєстрацію та авторизацію користувача
![photo1](/assets/labs/lab-3/1.jpg)
Реєстрація зроблена в app.js через маршрут POST /api/auth/register. Там беруться username, email, password, confirmPassword, role, перевіряються дані, хешується пароль і створюється користувач у БД.
![photo1](/assets/labs/lab-3/1_2.jpg)
![photo1](/assets/labs/lab-3/1_1.jpg)
Авторизація зроблена в app.js через POST /api/auth/login: користувач шукається по email, пароль звіряється через bcrypt.compare, після чого повертаються токени.


## Додати валідацію даних, обробку помилок
![photo1](/assets/labs/lab-3/2.jpg)
![photo1](/assets/labs/lab-3/2_1.jpg)

## Реалізувати захищений маршрут
![photo1](/assets/labs/lab-3/3.jpg)

## Проаналізувати отримані результати
реєстрація створює користувача в БД;
логін повертає токени;
захищений маршрут не працює без токена;
після logout refresh token очищується;
після кількох невдалих входів акаунт блокується;
при зміні email потрібне повторне підтвердження.

## Додати підтвердження пароля при реєстрації
![photo1](/assets/labs/lab-3/6.jpg)

## Додати роль користувача (admin/user)
![photo1](/assets/labs/lab-3/7.jpg)
![photo1](/assets/labs/lab-3/7_1.jpg)

## Реалізувати logout
![photo1](/assets/labs/lab-3/8.jpg)

## Додати оновлення профілю
![photo1](/assets/labs/lab-3/9.jpg)
Можна змінювати username і email. Якщо змінюється email, то emailVerified скидається в false і генерується новий токен підтвердження.

## Зберігати користувачів у базі
![photo1](/assets/labs/lab-3/10.jpg)

## Реалізувати refresh token
![photo1](/assets/labs/lab-3/11.jpg)
![photo1](/assets/labs/lab-3/11_1.jpg)
Хеш refresh token зберігається в полі refreshToken моделі User.

## Додати логування помилок
![photo1](/assets/labs/lab-3/12.jpg)

## Обмежити кількість спроб входу
![photo1](/assets/labs/lab-3/13.jpg)
![photo1](/assets/labs/lab-3/13_1.jpg)

## Додати middleware для перевірки токена
![photo1](/assets/labs/lab-3/14.jpg)

## Реалізувати зміну пароля
![photo1](/assets/labs/lab-3/15.jpg)

## Реалізувати видалення користувача
![photo1](/assets/labs/lab-3/16.jpg)

## Реалізувати відновлення пароля
![photo1](/assets/labs/lab-3/17.jpg)
![photo1](/assets/labs/lab-3/17_1.jpg)

## Додати підтвердження email
![photo1](/assets/labs/lab-3/18.jpg)
