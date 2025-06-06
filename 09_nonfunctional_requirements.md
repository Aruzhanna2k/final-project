# Нефункциональные требования

> Ниже представлены нефункциональные требования для продукта

| Требование          | Описание |
|------|------|
| **Производительность** | Время отклика пользовательского интерфейса не должно превышать 200 мс. Время ответа API, в свою очередь, не более 100 мс. Тестируется на наборах типичных пользовательских сценариев, также с помощью нагрузочного тестирования |
| **Доступность**        | Система должна быть доступна не менее 99% времени в месяц. С отдельным SLA (99.5%) на ключевые самые ключевые функции (см. https://github.com/Aruzhanna2k/final-project/blob/main/07_critical_scenarios.md). Используется мониторинг доступности и алерты в случае нарушения SLA. |
| **Масштабируемость**   | Архитектура системы должна обеспечивать масштабирование до 1 млн MAU без деградации производительности. Ключевые сервисы и их хранилища должны поддерживать горизонтальное масштабирование. |
| **Безопасность**       | Система должна использовать аутентификацию OAuth2 с JWT. Необходимо шифровать все чувствительные данные. |
| **Поддерживаемость**   | Покрытие автотестами не менее 70% кода. Наличие CI/CD с прогоном тестов. Используются подходы модульной архитектуры для минимизации связности между компонентами. |
| **Удобство развертывания** | Поддержка Zero-downtime деплоя с использованием blue-green стратегий, для плавного релиза новой версии. Наличие изолированных окружений (dev, stage, prod) для удобства тестирования. |
| **Совместимость**      | Система должна корректно работать с распространёнными BLE-устройствами. На этапе MVP реализация на кросс-платформенном стеке с минимизацией platform-specific зависимостей, для экономии ресурсов. |
| **Наблюдаемость**      | Все ключевые сервисы логируются и мониторятся после релиза. Используются Grafana (метрики), Kibana (логи), Alertmanager для уведомлений об аномалиях. Бизнес-метрики отправляются и хранятся в Amplitude. |
| **Локализация**        | Система должна поддерживать русский, английский языки на этапе MVP. Вся текстовая информация вынесена в админ-панель, что позволить добавлять новые языки без внесений изменений в код. |
