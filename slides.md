---
theme: seriph
background: https://cover.sli.dev
title: Знакомство с Aiogram
class: text-center
highlighter: shiki
transition: slide-left
---

## Aiogram - библиотека для построения бота для Telegram


---
transition: fade-out
---

# Основные темы этого месяца:

<v-clicks>

- телеграм боты
- организация кода
- работа с базой данных
- парсинг сайтов
- асинхронный код

</v-clicks>

---
transition: slide-up
---

# Важные моменты:

<v-clicks>

- файл `.gitignore` (он должен быть создан в первую очередь)
- названия файлов и папок в проекте(никаких `lesson1.py`, `lesson2.py`, `homework3.py` и т.д.)
- один проект в течение всего месяца

</v-clicks>

---

# Создание бота

<div>
    <ul>
        <li v-click>ищем в приложении Telegram бота с ником BotFather</li>
        <li v-click>создаем бота</li>
        <li v-click>задаем название</li>
        <li v-click>задаем ник</li>
        <li v-click>можно установить картинку и другие настройки</li>
    </ul>
</div>

---
transition: fade-out
---

# Создание проекта(папки) для бота

<v-clicks depth="2">

- активируем виртуальное окружение
- устанавливаем зависимости:
    - `aiogram` - [библиотека для построения бота](https://docs.aiogram.dev/en/latest/)
    - `python-dotenv` - [библиотека](https://pypi.org/project/python-dotenv/) для работы с `.env` файлами

</v-clicks>

---
transition: fade-out
---

# Создание проекта(папки) для бота

- файл `.gitignore`
- файл `main.py`
- файл `.env`

---

# Файл `.gitignore`

- Заходим на сайт [gitignore.io](https://www.gitignore.io/)
- Вбиваем `python` и жмем кнопку
- Копируем всё в файл `.gitignore`

---

# Файл `.env`

<ul>
    <li v-click>Для хранения <span v-mark="{ at: 6, color: 'yellow', type: 'highlight' }">конфиденциальных</span> данных, которые используются в проекте</li>
        <ul class="ml-8 list-disc">
            <li v-click>токен бота</li>
            <li v-click>логины и пароли от баз данных</li>
            <li v-click>IP-адреса</li>
        </ul>
    <li v-click><span v-mark="{ at: 6, color: 'red', type: 'circle' }">Не должен попадать</span> на гитхаб(гитлаб и т.д.)</li>
    <li v-click="'+2'">Копируем токен, который выдал @BotFather в этот файл</li>
</ul>
