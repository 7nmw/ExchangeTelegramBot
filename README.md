# TelegramBot
Бот возвращает цену на определённое количество валюты (евро, доллар или рубль).

При написании бота использована библиотека pytelegrambotapi.

Человек должен отправить сообщение боту в виде <имя валюты, цену которой он хочет узнать> <имя валюты, в которой надо узнать цену первой валюты> <количество первой 
валюты>.

При вводе команды /start или /help пользователю выводятся инструкции по применению бота.

При вводе команды /values выводиться информация о всех доступных валютах.

Для получения курса валют использована API и отправляющая к нему запросы с помощью библиотеки Requests.

Для парсинга полученных ответов использована библиотека JSON.

При ошибке пользователя (например, введена неправильная или несуществующая валюта или неправильно введено число) вызывается собственное исключение APIException с текстом пояснения ошибки.

Текст любой ошибки с указанием типа ошибки отправляеться пользователю в сообщения.

Для отправки запросов к API описан класс со статическим методом get_price(), который принимает три аргумента и возвращает нужную сумму в валюте:

имя валюты, цену на которую надо узнать, — base;

имя валюты, цену в которой надо узнать, — quote;

количество переводимой валюты — amount.

Токен Telegram-бота храниться в специальном конфиге.

Все классы спрятаны в файле extensions.py.
