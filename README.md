# Mission 3

# Buildship
https://drive.google.com/file/d/1ggzfs_AMyLNqlaoCuf-kKAcrjrU58UYq/view?usp=sharing

# Selects
```sql
Получить список юзернеймов пользователей
SELECT username FROM users;

Получить кол-во отправленных сообщений каждым пользователем
SELECT from_username, COUNT(id) AS number_of_sent_messages
FROM messages
GROUP BY from_username; 

Получить пользователя с самым большим кол-вом полученных сообщений и само количество
SELECT to_username, COUNT(id) AS "number of received messages"
FROM messages
GROUP BY to_username
ORDER BY "number of received messages" DESC
LIMIT 1;

Получить среднее кол-во сообщений, отправленное каждым пользователем
SELECT username, AVG(number_of_sent_messages) AS average_sent_messages
FROM (
    SELECT from_username AS username, COUNT(*) AS number_of_sent_messages
    FROM messages
    GROUP BY from_username
) AS sent_messages_per_user
GROUP BY username;
```
