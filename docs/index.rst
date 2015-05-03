Flask-Security
==============

Flask-security позволяет быстро добавлять механизмы безопасности для вашего приложения. Он включает в себя:

1. Аутентификация на основе сессии
2. Управление ролями (группами пользователей)
3. Шифрование пароля
4. HTTP-аутентификацию
5. Токен аутентификацию
6. Активация учетной записи на основе токена (опционально)
7. Токен восстановления/сброса пароля (опционально)
8. Регистрация пользователей (опционально)
9. Отслеживание входа (опционально)
10. Поддержка JSON/AJAX

Многие из этих функций стали возможными благодаря интеграции с различными flask-расширениями и библиотеками. А именно:

1. `Flask-Login <https://flask-login.readthedocs.org/en/latest/>`_
2. `Flask-Mail <http://packages.python.org/Flask-Mail/>`_
3. `Flask-Principal <http://packages.python.org/Flask-Principal/>`_
4. `Flask-Script <http://packages.python.org/Flask-Script/>`_
5. `Flask-WTF <http://packages.python.org/Flask-WTF/>`_
6. `itsdangerous <http://packages.python.org/itsdangerous/>`_
7. `passlib <http://packages.python.org/passlib/>`_

Кроме того, предполагается, что вы будете использовать одну из представленных ниже библиотек, для соединения с базой данных и определения моделей. Flask-Security поддерживает следующие расширения из коробки:

1. `Flask-SQLAlchemy <http://pypi.python.org/pypi/flask-sqlalchemy/>`_
2. `Flask-MongoEngine <http://pypi.python.org/pypi/flask-mongoengine/>`_
3. `Flask-Peewee <http://pypi.python.org/pypi/flask-peewee/>`_


.. include:: contents.rst.inc
