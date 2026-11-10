BUG-006
Заголовок:
POST /auth: неверные учётные данные возвращают 200 OK вместо кода ошибки
Окружение: Postman 12.25, macOS 15.7.7, https://restful-booker.herokuapp.com
Шаги:
1. Создать запрос POST https://restful-booker.herokuapp.com/auth
2. Заголовок Content-Type: application/json
3. Тело: { "username": "admin", "password": "111password123456" }
4. Нажать Send
Ожидаемый результат:
Код ошибки аутентификации (401), в теле нет токена.
Фактический результат:
200 OK, тело {"reason": "Bad credentials"}. Токен не выдан.
Для сравнения: с верными данными 200 и поле token.
Severity:
Minor: доступ не получен, но статус не отражает провал авторизации
Priority:
Low: клиенты могут обойти это проверкой тела, сервис работает
Воспроизводимость: 3 из 3

<img width="953" height="644" alt="Снимок экрана 2026-11-10 в 22 27 36" src="https://github.com/user-attachments/assets/092ec85d-3530-414f-9a5f-3a0988294250" />
