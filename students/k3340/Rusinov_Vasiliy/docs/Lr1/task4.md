### Условие
Реализовать многопользовательский чат. Реализация
многопользовательского чата позволяет получить максимальное количество
баллов.

Реализовать с помощью протокола TCP – 100% баллов, с помощью UDP – 80%.
Обязательно использовать библиотеку threading.
Для реализации с помощью UDP, threading использовать для получения
сообщений у клиента.
Для применения с TCP необходимо запускать клиентские подключения И прием
и отправку сообщений всем юзерам на сервере в потоках. Не забудьте сохранять юзеров,
чтобы потом отправлять им сообщения.

### Запуск 
Для запуска сервера  ``` python server.py ```

Для запуска клиентов  ``` python client.py ```

Сервер создает сокет и ожидает подключения клиентов.
Для каждого нового клиента запускается отдельный поток, в котором сервер получает сообщения от этого клиента и передает их другим клиентам через функцию broadcast.
Когда клиент отключается, его сокет удаляется из списка клиентов.

Клиент подключается к серверу и отправляет ему сообщения.
Сообщения, которые сервер передает другим клиентам, клиент получает в отдельном потоке через функцию receive_messages.