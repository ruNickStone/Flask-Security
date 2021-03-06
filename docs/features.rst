Особенности
========

Flask-security позволяет быстро добавлять общие механизмы безопасности для вашего приложения. Он включает в себя:


Аутентификация на основе сессии
----------------------------

Аутентификация на основе сессии осуществляется исключительно за счет расширения `Flask-Login`_. Flask-Security автоматически обрабатывает конфигурацию Flask-Login на основе нескольких собственных конфигурационных значений и использует `Flask-Login токен`_ для запоминания пользователей, когда их сессия истекла.


Role/Identity Based Access
--------------------------

Flask-Security реализует очень простое управление группами пользователей из коробки. Это означает, что вы можете привязать к одному пользователю, как высокий уровень привилегий, так и несколько ролей сразу. Например, вы можете назначить следующие роли пользователям: администратор, редактор, суперпользователь, или их комбинацию. Контроль доступа на основе ролей и все их имена должны быть уникальными. Эта функция реализуется с помощью расширения `Flask-Principal`_. Если вы хотели бы осуществлять более продвинутый контроль доступа, вы можете обратиться к Flask-Principal `документации`_.


Шифрование паролей
-------------------

Шифрование паролей реализовано через `passlib`_. По умолчанию, пароли хранятся в виде обычного текста, но вы можете легко настроить алгоритм шифрования. Вы должны всегда использовать алгоритм шифрования в вашем приложении, подробнее вы можете прочитать в моей статье.


HTTP-аутентификация
-------------------------

HTTP-аутентификация использует простой декоратор. Эта функция ожидает входящие данные аунтификации для идентификации пользователя в системе. Это означает, что имя пользователя должно быть равно адресу его электронной почты.


Токен авторизации
--------------------

Проверка авторизации на основе токена включена путем извлечения токена аутентификации пользователя, путем отправки HTTP POST с деталями аутентификации. Успешный запрос вернет ID пользователя и токен аутентификации. Этот токен может быть использован в последующих запросах к защищенным ресурсам. Токен аутентификации передается в запросе через HTTP-заголовки или в GET параметрах. По умолчанию, имя HTTP-заголовка Authentication-Token, а стандартное имя GET параметра auth_token. Токены аутентификации генерируются с помощью пароля пользователя. Таким образом, если изменяется пароль пользователя, то существующий токен становится недействительным. Соответственно, новый токен будет получен уже с помощью нового пароля пользователя.


Подтверждающее письмо о регистрации
------------------

При желании вы можете потребовать, чтобы новый пользователь подтвердил, указанный при регистрации, адрес электронной почты. Flask-Security будет отправлять email-сообщение для этого пользователя, с ссылкой для подтверждения своего аккаунта. После перехода по ссылке, пользователь будет автоматически зарегистрирован. Так же, существует возможность для повторной отправки подтверждающей ссылки, если пользователи пытался активировать уже просроченный токен или при потере доступа к предыдущему email-адресу.


Сброс/восстановление пароля
-----------------------

Flask-Security отправляет сообщение электронной почты пользователю со ссылкой, по которой они могут сбросить свой пароль. Когда пароль будет сброшен, они автоматически войдут в систему и с того момента, смогут использовать новый пароль.


Регистрация пользователя
-----------------

Flask-Security предоставляет функционал регистрации пользователей. Это очень просто, ведь для регистрации нового пользователя необходимо ввести только адрес своей электронной почты и пароль. Количество полей можно легко изменить, если ваш процесс регистрации требует больше данных.


Логгирование
--------------

Flask-Security, если настроен на эту опцию, может отслеживать основные события входа в систему. А именно:

* Дата последнего входа в систему
* Время текущего входа
* Последний IP адрес
* Текущий IP адрес
* Общее количество авторизаций


Поддержка AJAX/JSON
-----------------

Flask-Security поддерживает формат json/AJAX-запросов там, где это уместно. Просто помните, что все конечные точки требуют csrf-токен. Более конкретно, json поддерживается для следующих запросов:

* Login requests
* Registration requests
* Change password requests
* Confirmation requests
* Forgot password requests
* Passwordless login requests


.. _Flask-Login: http://packages.python.org/Flask-Login/
.. _alternative token: http://packages.python.org/Flask-Login/#alternative-tokens
.. _Flask-Principal: http://packages.python.org/Flask-Principal/
.. _documentation on this topic: http://packages.python.org/Flask-Principal/#granular-resource-protection
.. _passlib: http://packages.python.org/passlib/
