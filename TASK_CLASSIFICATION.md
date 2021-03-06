# Классификация видов задач в публичном трекере 1С:EDT

В данном документе представлена актуальная классификация задач публичного трекера 1С:EDT

- Классификация:
  - [Критическая ошибка](#критическая-ошибка)
    - [Не является критической ошибкой](#не-является-критической-ошибкой)
  - [Ошибка](#ошибка)
    - [Не является ошибкой 1С:EDT](#не-является-ошибкой-1cedt)
  - [Пожелание](#пожелание)
- [Принципы приоритизации задач в публичном трекере 1С:EDT](#принципы-приоритизации-задач-в-публичном-трекере-1сedt)

### Критическая ошибка

Ошибка, приводящая к невозможности использования 1C:EDT в процессе разработки:
- Безусловные
  - Зависание 1С:EDT либо каких-либо его процессов
  - Невозможность публикации в/из ИБ без наличия соответствующего сообщения от подсистемы валидации
  - Потеря/нарушение данных (в основной конфигурации, в расширениях), обнаруженная постфактум
  - Стабильное падение редактора/стабильное не открытие редактора какого-либо объекта
  - Полный временный отказ основной функции (например отвал сессии дебага и т.п.), без описывающего проблему понятного сообщения
  - Продолжительное около-100% потребление процессора процессом 1С:EDT без заметного прогресса текущей операции/при отсутствии видимых прогресс-баров
- Условные
  - Проблемы, выявленные в рамках процесса community-апробации RC, являющиеся регрессией относительно предыдущей версии (по результатам объективного сравнительного тестирования, а не мнения пользователей)
  - Проблемы массового характера, не попадающие под вышеуказанные критерии, но значительно уменьшающие productivity (потеря часов рабочего времени за период). Конечный уровень критичности при необходимости определяется командой EDT коллегиально

#### Не является критической ошибкой

- Отличия лэйаута (отображения) отдельной формы от конфигуратора при отсутствии нарушений в данных формы
- Невозможность редактирования отдельного свойства объекта (без порчи данных)
- Медленная работа отдельных операций (кроме случаев, подпадающих под критерии проблемы массового характера)
- Ошибки в полнотекстовом поиске
- Отсутствие отдельных полей/методов в подсказе при редактировании модулей
- Отдельные неверно определенные ошибки в проверках
- Отдельные исключения в журнале системы, не приведшие к видимым проблемам
- "Лишние" изменения в исходниках 1C:EDT, не приводящие к нарушению нормального функционирования системы

Являются критическими, официально признаны, но не могут быть устранены оперативно:
- Медленная публикация в ИБ (на текущем этапе, проблема известна, работаем над ней)
- Медленная отладка (на текущем этапе, проблема известна, работаем над ней)

### Ошибка

Прочие ошибки, не попадающие под критерии критических ошибок:
- Несоответствие поведения системы ранее заявленной/утвержденной спецификации
- Ошибки дизайна/usability, которые мешают нормальной работе
- Ошибки в оформлении (описки, и т.п.)
- Одиночные отказы (на отдельных объектах)
- Частичная неработоспособность функций, которую можно компенсировать временной (до исправления проблемы) работой в конфигураторе 1С:Платформы
- И т.п.

#### Не является ошибкой 1С:EDT

- Отличие поведения какого-либо механизма от аналогичного механизма в конфигураторе в случае, если не приводит к созданию невалидных данных/порче данных
- Отличие поведения какого-либо механизма от "общепринятых стандартов", "конкурирующих продуктов" и т.п.
- Порча данных и последующая некорректная работа 1С:EDT (но без критических последствий, см. выше) в результате использования сторонних инструментов

### Пожелание

- Любой запрос на улучшение существующей функциональности, документации, UX. 
- Также к пожеланиям относятся запросы на новые функции в 1C:EDT.

## Принципы приоритизации задач в публичном трекере 1С:EDT

Приоритет задачи/пожелания при планировании/реализации определяется (в порядке убывания значимости факторов):
- Критичностью/некритичностью ошибки с т.з. формальных параметров (приведены ранее)
- Текущими планами 1С:EDT по обязательным направлениям разработки (стабилизация продукта по результатам внутреннего тестирования, поддержка новых версий платформы 1С, стратегические задачи по развитию 1C:EDT, оптимизация работы приложения по скорости/потреблению ресурсов)
- Рейтингом проблемы/пожелания в сообществе
- Размером аффектированной группы пользователей
- Наличием/отсутствием технических ограничений в EDT. Ограничения обычно выявляются в ходе фазы анализа, однако могут служить и причиной изменения приоритета уже в ходе реализации
