- 🧑‍💼 **Admin** – повний доступ, управління користувачами
- 🧑‍🔧 **Manager** – CRUD для власних оголошень
- 👤 **Client** – коментування постів
- 👀 **Guest** – лише читання

## 🚀 Швидкий старт

```bash
npm install
npm start
```

> API доступне за адресою: `http://localhost:4000`

## 🔐 Аутентифікація

- Access Token (15 хвилин) — зберігається в памʼяті
- Refresh Token (7 днів) — зберігається в httpOnly cookie
- 🔁 Автоматичне оновлення токенів через RTK Query `baseQueryWithReauth`

---

## 📁 API Документація

### 🔐 Auth

| Метод | Роут                | Опис                             |
| ----- | ------------------- | -------------------------------- |
| POST  | `/api/auth/login`   | Логін, токени в пам'ять + cookie |
| POST  | `/api/auth/refresh` | Оновити Access Token             |
| POST  | `/api/auth/logout`  | Очистити cookie                  |

### 👥 Users

| Метод | Роут             | Роль     | Опис                     |
| ----- | ---------------- | -------- | ------------------------ |
| GET   | `/api/users/`    | admin    | Список усіх користувачів |
| GET   | `/api/users/:id` | будь-хто | Профіль користувача      |

### 📢 Posts

| Метод | Роут             | Роль        | Опис                 |
| ----- | ---------------- | ----------- | -------------------- |
| GET   | `/api/posts/`    | будь-хто    | Список постів        |
| POST  | `/api/posts/`    | manager     | Додати новий пост    |
| PUT   | `/api/posts/:id` | author only | Редагувати свій пост |

### 💬 Comments

| Метод | Роут                   | Роль     | Опис                        |
| ----- | ---------------------- | -------- | --------------------------- |
| GET   | `/api/comments/`       | будь-хто | Отримати всі коментарі      |
| GET   | `/api/comments?postId` | будь-хто | Отримати коментарі до поста |
| POST  | `/api/comments/`       | client   | Додати коментар до поста    |

---

## 🧪 Користувачі (тестові)

| Email                | Пароль   | Роль    |
| -------------------- | -------- | ------- |
| admin@example.com    | admin123 | admin   |
| manager1@example.com | admin123 | manager |
| manager2@example.com | admin123 | manager |
| client1@example.com  | admin123 | client  |
| client2@example.com  | admin123 | client  |

---
