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
- файл `.env`
- файл `main.py`

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

---

# Файл `main.py`

<hidden-todo
    :todos="[
        'Обработчик всех сообщений бота',
        'Обработчик команды `/start`',
    ]"
/>

---

# Вопросы для повторения

<Questions
:questions="[
        {
            q: 'Что такое бот в Telegram?',
            a: [
                'Асинхронный код',
                'Библиотека',
                'Специальный аккаунт, которого можно запрограммировать для взаимодействия с другими пользователями',
                'Не знаю'
            ],
            correct: 2
        },
        {
            q: 'Что из нижеперечисленного является командой для бота?',
            a: [
                'Кнопка',
                'Сообщения, начинающиеся с \'/\', пример: \'/start\' или \'/help\'',
                'Любые сообщения',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Для чего нужен токен для телеграм бота?',
            a: [
                'Он не нужен',
                'Для работы с базами данных',
                'Это как \'логин-пароль\' для бота, чтобы Telegram отличал ботов между собой',
                'Не знаю'
            ],
            correct: 2
        },
        {
            q: 'Что такое aiogram?',
            a: [
                'Библиотека для построения бота',
                'Telegram бот',
                'Не знаю'
            ],
            correct: 0
        },
        {
            q: 'Что такое python-dotenv?',
            a: [
                'Бибилиотека для отправки картинок',
                'Библиотека для работы с `.env` файлами',
                'Библиотека для работы с базами данных',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Для чего нужен файл `.env`?',
            a: [
                'Для работы с базами данных',
                'Для хранения конфиденциальных данных',
                'Для отправки картинок',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Для чего используют декораторы в Aiogram?',
            a: [
                'Для работы с базами данных',
                'Для привязки определенных команд, сообщений и т.д. к определенным функциям',
                'Для хранения конфиденциальных данных',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Что такое обработчик в Aiogram?',
            a: [
                'Это функция для обработки сообщений',
                'Это пользователь',
                'Это название бота',
                'Не знаю'
            ],
            correct: 0
        },
        {
            q: 'Что такое диспетчер в Aiogram?',
            a: [
                'Это функция для обработки определенных сообщений',
                'То, что связывает входящие сообщения с обработчиками',
                'Это название бота',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Как запустить бота?',
            a: [
                'await bot.polling()',
                'async dispatcher.start_polling()',
                'await dispatcher.start_polling(bot)',
                'await bot.start_polling(dispatcher)',
            ],
            correct: 2
        },
        {
            q: 'Как записать декоратор для функции, которая будет обрабатывать все сообщения?',
            a: [
                '@dp.message()',
                '@dp.message(Command(\'start\'))',
                '@dp.message(Command(\'help\'))',
                'Не знаю'
            ],
            correct: 0
        },
        {
            q: 'Как записать декоратор для функции, которая будет обрабатывать команду `/random_recipe`?',
            a: [
                '@dp.message(Command(\'start\'))',
                '@dp.message(Command(\'random_recipe\'))',
                '@dp.message()',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Как из входящего сообщения(message) получить уникальный идентификатор пользователя?',
            a: [
                'message.user.id',
                'message.from_user.id',
                'message.from_user.first_name',
                'message.user_id',
                'Не знаю'
            ],
            correct: 1
        },
        {
            q: 'Как из входящего сообщения(message) получить текст этого сообщения?',
            a: [
                'message.from_user.first_name',
                'message.from_user.text',
                'message.text',
                'message.message'
            ],
            correct: 2
        },
        {
            q: 'Как сделать так, чтобы бот отправил ответ пользователю?',
            a: [
                'await message.answer(\'Привет!\')',
                'await message(\'Привет!\')',
                'await message.send(\'Привет!\')',
                'await message.message(\'Привет!\')',
            ],
            correct: 0
        }
    ]"
/>
