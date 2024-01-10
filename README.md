#### Server: <a href="https://ra-8-3-hooks-context-authentication.onrender.com/">Render</a>

# Authentication

Вы решили построить систему с аутентификацией.

Используя сервер, расположенный в каталоге `backend`, реализуйте следующее приложение, удовлетворяющее следующим условиям:

1. При первой загрузке показывается Landing-страница с формой входа:

![](./assets/unauthenticated.png)

2. После авторизации (POST http://localhost:7070/auth `{"login": "vasya", "password": "password"}`), загружаются компонент ленты новостей и в тулбаре отображается профиль с кнопкой выйти:

![](./assets/authenticated.png)

Для запроса профиля используйте запрос вида:
```
GET http://localhost:7070/private/me
Authorization: Bearer <ваш_токен>
```

Для запроса новостей используйте запрос вида:
```
GET http://localhost:7070/private/news
Authorization: Bearer <ваш_токен>
```

Важно:
1. Профиль и токен должны храниться в localStorage/sessionStorage (при перезагрузке страницы должна так же загружаться лента новостей, если мы аутентифицированы)
1. Должна быть обработка ошибок, если получена ошибка 401 - то нужно разлогинивать пользователя (удалять всё из localStorage/sessionStorage)
1. Не используйте React Router, просто подменяйте компоненты в зависимости от текущего состояния аутентификации.
