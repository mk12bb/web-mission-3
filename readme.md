# Mission 3

## Часть 1 / Часть 2

[Link to video](https://www.loom.com/share/cc4f776d38214e7b963bfa49b4c53d36?sid=b07fc095-a3a4-4666-b679-bb9dbcb87a1c)

## Часть 3 - select'ы

- Задание 1. Получить список юзернеймов пользователей	 
> SELECT username FROM users  

- Задание 2. Получить кол-во отправленных сообщений каждым пользователем
> SELECT 
  "from" AS user_id,
  COUNT(*) AS number_of_sent_messages
FROM messages
GROUP BY "from 

- Задание 3. Получить пользователя с самым большим кол-вом полученных сообщений и само количество
> SELECT 
  "to" AS user_id,
  COUNT(*) AS number_of_received_messages
FROM messages
GROUP BY "to"
ORDER BY number_of_received_messages DESC
LIMIT 1


- Задание 4. Получить среднее кол-во сообщений, отправленное каждым пользователем
> SELECT 
  ROUND(COUNT(*) * 1.0 / COUNT(DISTINCT "from"), 2) AS avg_messages_per_user
FROM messages
