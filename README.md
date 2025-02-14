# Использование секрета Yandex Lockbox для хранения статического ключа доступа

Если вы часто используете сервисы с AWS-совместимым API, например [Yandex Object Storage](https://yandex.cloud/ru/docs/storage/), [Yandex Data Streams](https://yandex.cloud/ru/docs/data-streams/) или [Yandex Message Queue](https://yandex.cloud/ru/docs/message-queue/), вам приходится самостоятельно заботиться о безопасном хранении [статических ключей доступа](https://yandex.cloud/ru/docs/iam/concepts/authorization/access-key).

В данном руководстве рассматривается сценарий, при котором в качестве хранилища для статического ключа доступа используется [секрет](https://yandex.cloud/ru/docs/lockbox/concepts/secret) Yandex Lockbox. При этом значение ключа доступа не только не хранится локально на компьютере пользователя, но и не выводится на экран.

При обращении к ресурсу AWS-совместимого сервиса (Object Storage) статический ключ доступа и его идентификатор будут извлекаться из секрета Yandex Lockbox в специальные переменные окружения, которые будут использоваться для аутентификации запроса.

Такой подход позволит обеспечить безопасность хранения ключа и его использования при обращении к сервисам.

Создание инфраструктуры с помощью Terraform описано в [практическом руководстве](https://yandex.cloud/ru/docs/iam/tutorials/static-key-in-lockbox/terraform), необходимый для настройки конфигурационный файл `static-key-in-lockbox-config.tf` расположен в этом репозитории.
