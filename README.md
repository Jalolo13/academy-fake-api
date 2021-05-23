# Fake api для студентов IT Academy

Для запуска сервера сначала установите все зависимости используя команду
```
npm install
```
После этого запускаем сервер командой
```
npm start
```
Сервер будет запущен на порту 1717 (http://localhost:1717)

## Доступные CRUD приложения и роуты
  
Книги `/books`
<br/>
Кондитерская `/pastry`
<br/>
Кафе и рестораны `/eats`
<br/>
Студенты `/students`
<br/>

#### Как пользоваться данным АПИ
Вместо слова `resource` вставте нужный вам url. Например, если вам нужны книги используйте `/books`    
<br/>
**Для получения списка всех элементов**  
`GET /resource`

**Для получения одной книги по id**  
`GET /resource/detail/:id`

**Для создания новой книги**  
`POST /resource/create`
id объекта сгерерируется на сервере  

**Для редактирования книги**  
`PUT /resource/update/:id`  

**Для удаления книги**  
`DELETE /resource/delete/:id`  
При успешном удалении вы получите сообщение  
```
successfull delete
```
## Авторизация и регистрация пользователя

**Для получения данных о пользователе**  
В заголовке "X-Auth" должен передаваться токен. Если токен не корректен или отсутствует, в ответе придет ошибка 403
`GET /me`
в успешном ответе придет объект
```
  username: string
  firstName: string (optional)
  age: number (optional)
```


**Для регистрации нового пользователя**  
`POST /signin`
в body должен приходить объект вида
```
  username: string
  password: string
  firstName: string (optional)
  age: number (optional)
```
в ответе придет объект
```
  token: string // токен 
  data: object // вся известная информация о юзере
```

**Для авторизации**  
`POST /login`
в body должен приходить объект вида
```
  username: string
  password: string
```
в ответе придет объект
```
  token: string // токен 
  data: object // вся известная информация о юзере
```

