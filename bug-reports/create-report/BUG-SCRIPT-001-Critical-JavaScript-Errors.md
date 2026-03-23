# Баг-репорт BUG-SCRIPT-001

## Название
Критические ошибки JavaScript при загрузке страницы — `supabase` объявлен дважды, `onAuthStateChange` не определён

| Проект | BugReportery |
|--------|----------------|
| Серьёзность | Critical |
| Приоритет | High |
| Тип бага | JavaScript / Инициализация |
| Статус | Открыт |

## Описание
При загрузке главной страницы https://bugreportery.qatest.tech в консоли браузера возникают ошибки, связанные с повторным объявлением переменной `supabase` и вызовом неопределённого метода `onAuthStateChange`. Это может нарушать работу всех последующих скриптов, включая формы регистрации и создания баг-репортов.

## Окружение
- **Устройство:** Desktop
- **ОС:** Windows 11 Pro
- **Браузер:** Яндекс Браузер 25.12.4.1216 (64‑бит) / Google Chrome 146.0.7680.80 (64‑бит)
- **URL:** https://bugreportery.qatest.tech

## Шаги воспроизведения
1. Открыть инструменты разработчика (F12) → вкладка Console
2. Очистить консоль (если нужно)
3. Обновить страницу (F5)

## Фактический результат
В консоли отображаются ошибки:
(индекс):182 Uncaught SyntaxError: Identifier 'supabase' has already been declared (at (индекс):182:13)
form.js:110 Uncaught TypeError: Cannot read properties of undefined (reading 'onAuthStateChange')
at HTMLDocument.<анонимная> (form.js:110:19)



## Ожидаемый результат
Загрузка страницы не должна вызывать ошибок JavaScript. Все переменные и методы должны быть объявлены единожды и корректно инициализированы.

## Вложения

- **Скриншот ошибок в консоли:** [bug-script-001-console-error.png](../attachments/create-report/bug-script-001-console-error.png)
- **Лог консоли:** [bug-script-001-console-error.log](../attachments/create-report/bug-script-001-console-error.log)
- **HAR-файл:** [bug-script-001-network.har](../attachments/create-report/bug-script-001-network.har)