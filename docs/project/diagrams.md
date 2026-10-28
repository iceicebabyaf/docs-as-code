# Диаграммы
## Диаграмма последовательности
```mermaid
sequenceDiagram
    actor User as Пользователь
    participant System as Система
    participant Model as ML-модель

    User->>System: Отправить текст
    System->>System: Проверить текст и его длину
    System->>Model: Передать текст для обработки
    Model-->>System: Вернуть краткий пересказ
    System-->>User: Показать результат
```
---
## Диаграмма классов
```mermaid
classDiagram
    class User {
        +int id
        +string name
        +viewHistory()
    }

    class TextDocument {
        +int id
        +string text
        +validateLength()
    }

    class Summary {
        +int id
        +string content
        +datetime createdAt
    }

    class Model {
        +string modelName
        +generateSummary(text)
    }

    User "1" --> "*" TextDocument : отправляет
    TextDocument "1" --> "1" Summary : имеет
    Model ..> TextDocument : обрабатывает
    Model ..> Summary : создаёт
```