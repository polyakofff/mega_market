# mega_market

Сделаны 3 основные ручки (imports, delete, nodes).

Приложение работает на java сервлетах с использованием веб-сервера tomcat. База данных выбрана postgresql. Основным фреймворком выбран spring. Система сборки - maven.

При обращении к ручкам в названии надо прописать megamarket (\*/megamarket/imports) (тонкости tomcat'а). Приложение работает на порте 80, однако так как после дедлайна доступ к машинке у меня еще был, я решила поэксперементировать и в файлике ~/apache-tomcat-9.0.64/conf/server.xml порт 80 исправила на 8080 (и забыла вернуть обратно). Поэтому сейчас при обращении к ручкам будут сыпаться 503: Service Unavailable.
Еще не совсем получилось реализовать автоматический запуск при рестарте машинки, потому что к порту 80 могут обращаться лишь пользователи с root правами (в отличие от 8080).
Тестирование осуществлялось локально на spring-профиле dev.

Чтобы запустить сервис, надо (помимо того, что исправить 8080 на 80 в файле server.xml) запустить команду: **sudo /etc/init.d/tomcat start**. Запрос, проверяющий, что все работает: **https://resulting-2005.usr.yandex-academy.ru/megamarket/home**.
