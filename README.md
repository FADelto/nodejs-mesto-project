# Бэкенд Mesto

## Описание
REST API для сервиса Mesto — приложения для публикации фотографий. Реализована регистрация и авторизация пользователей, создание и удаление карточек, постановка и снятие лайков.

## Используемые технологии
- TypeScript
- Node.js
- Express.js
- MongoDB + Mongoose
- JWT-авторизация (jsonwebtoken)
- Хеширование паролей (bcryptjs)
- Валидация запросов (celebrate + Joi)
- Валидация данных на уровне схем (validator)
- Логирование (winston + express-winston)

## Структура проекта
```
src/
├── app.ts                    — точка входа
├── controllers/
│   ├── users.ts              — контроллеры пользователей
│   └── cards.ts              — контроллеры карточек
├── models/
│   ├── user.ts               — схема пользователя
│   └── card.ts               — схема карточки
├── routes/
│   ├── users.ts              — роуты пользователей
│   └── cards.ts              — роуты карточек
├── middlewares/
│   ├── auth.ts               — middleware авторизации
│   ├── error-handler.ts      — централизованная обработка ошибок
│   └── logger.ts             — логирование запросов и ошибок
└── errors/
    ├── bad-request-error.ts  — 400
    ├── unauthorized-error.ts — 401
    ├── forbidden-error.ts    — 403
    ├── not-found-error.ts    — 404
    └── conflict-error.ts     — 409
```

## Роуты

### Пользователи
- `POST /signup` — регистрация
- `POST /signin` — авторизация
- `GET /users` — получить всех пользователей
- `GET /users/me` — получить текущего пользователя
- `GET /users/:userId` — получить пользователя по ID
- `PATCH /users/me` — обновить профиль
- `PATCH /users/me/avatar` — обновить аватар

### Карточки
- `GET /cards` — получить все карточки
- `POST /cards` — создать карточку
- `DELETE /cards/:cardId` — удалить карточку
- `PUT /cards/:cardId/likes` — поставить лайк
- `DELETE /cards/:cardId/likes` — снять лайк

## Запуск

```bash
npm install
npm run dev
```

## Скрипты
- `npm run dev` — запуск в режиме разработки
- `npm run start` — запуск сервера
- `npm run build` — сборка проекта
- `npm run lint` — проверка линтером
