# Architectural Decision Records (ADR)

> Ниже представлен список архитектурных решений, принятых в рамках реализации продукта.

1. **Обоснование выбора архитектурного стиля модульный монолит с DDD**
   - Решение о построении системы в виде модульного монолита с четким разделением доменов по принципам Domain-Driven Design (DDD). Сравнение данного выбора с другими, обоснование выбора монолита. Определение планируемого потраченного бюджета на реализацию и поддержку.

2. **Метод авторизации: OAuth2 + JWT**
   - Решение использование OAuth2 как механизм авторизации, с JWT в качестве формата токенов. Сравнение метода авторизации с сессиями. Описать реализовацию stateless-аутентификации.

3. **Способ хранения данных**
   - Для основной бизнес-логики используется реляционная база данных с поддержкой транзакций и сложных запросов. Сравнение метода хранения данных с NoSQL. Определить, какие модули и бизнес-процессы вероятно будут использовать NoSQL.

4. **Интеграции с устройствами**
   - Во время тренировки данные с устройства передаются в реальном времени через gRPC или WebSocket. После завершения сессии необходима обработка данных и интеграции с другими сервисами выполняются асинхронно через Kafka для отказоустойчивости.

5. **Push-уведомления**
   - Все события, отправляемые пользователям публикуются через очередь сообщений. Необходимо спроектировать интеграцию сбора событий в топики, и обосновать выбор между брокерами Кafka/rabbitMQ.

6. **Механизм логирования и наблюдаемости**
    - Выбрать стек инструментов для сбора метрик, логов и трассировок. Подумать в сторону Prometheus + Grafana. Исследовать, выделить плюсы и минусы инструентов.
