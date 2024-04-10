---
cover: .gitbook/assets/wooden-desk-with-a-mouse.jpg
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Программа для отправки писем

## [Код](https://github.com/Vladislav-ff/wiki-test/tree/main/%D0%9F%D1%80%D0%BE%D0%B3%D0%B0) программы

***

## Структура страницы

* [Описание программы отправки электронной почты с помощью Python](./#opisanie-programmy-otpravki-elektronnoi-pochty-s-pomoshyu-python)
* [Введение](./#vvedenie)
* [Функциональность](./#funkcionalnost)
* [Использование](./#ispolzovanie)
* [Установка Python](./#ustanovka-python)
* [Установка необходимых библиотек](./#ustanovka-neobkhodimykh-bibliotek)
* [Получение пароля](./#poluchenie-parolya)
* [Пример использования](./#primer-ispolzovaniya)
* [Заключение](./#zaklyuchenie)
* [Подробнее про SMTP](./#bolee-podrobno-pro-smtp-mozhno-pochitat-zdes)

## Описание программы отправки электронной почты с помощью Python

### Введение

Эта программа написана на Python и предназначена для отправки электронной почты с использованием SMTP-сервера. Она использует модули `smtplib`, `getpass`, `email.mime.text`, `csv` и `sys` для чтения учетных данных, создания сообщений, чтения данных из CSV-файла и записи вывода в файл.

### Функциональность

#### Программа выполняет следующие основные функции:

1. Сначала программа считывает учетные данные из файла `my_email.txt`. Этот файл содержит адрес электронной почты в первой строке и пароль от этого электронного адреса во второй строке.
2. После этого программа открывает файл `таблица.csv` и читает данные из него. Каждая строка в этом файле предполагается содержать адрес получателя и текст сообщения, разделенные точкой с запятой.
3. Затем программа создает MIME-объект сообщения, указывая текст сообщения, отправителя, получателя и тему.
4. Далее программа устанавливает соединение с SMTP-сервером (в этом случае, используется SMTP-сервер Яндекса) через защищенное SSL-соединение, выполняет вход с использованием учетных данных из файла и отправляет сообщение каждому адресату из файла `таблица.csv`.
5. По мере отправки каждого сообщения программа также выводит информацию о отправителе, получателе, а также содержимом сообщения в файл `output.txt`. После отправки всех сообщений, программа закрывает соединение с SMTP-сервером.

### Использование

Чтобы использовать эту программу на разных операционных системах, необходимо выполнить следующие шаги:

1. [Установить Python](./#ustanovka-python) и [необходимые библиотеки](./#ustanovka-neobkhodimykh-bibliotek).
2. Создать файл `my_email.txt` и записать в него адрес электронной почты и пароль. ([Пример txt-файла](./#primer-soderzhimogo-txt-faila))
3. Создать файл `таблица.csv` и заполнить его данными, содержащими адреса электронных почт и текст сообщений. ([Пример CSV-файла](./#primer-soderzhimogo-csv-faila))
4. Запустить программу с помощью команды `python3 имя_файла.py` на Linux и macOS или `python имя_файла.py` на Windows.
5. Программа запишет информацию о отправителе, получателе, содержимом сообщения, а также техническую информацию в файл `output.txt`. ([Пример txt-файла](./#vot-primer-togo-chto-mozhet-byt-zapisano-v-fail-output.txt))

Вот [пример](./#primer-ispolzovaniya) использования этой программы.

Программа будет отправлять электронные письма на адреса, указанные в файле `таблица.csv`, с использованием адреса электронной почты и пароля, указанных в файле `my_email.txt`. Результаты отправки будут записываться в файл `output.txt`.

***

Для установки Python и необходимых библиотек на разных операционных системах, выполните следующие шаги:

### Установка Python

#### На Linux

* **Ubuntu и Debian**: выполните следующие команды в терминале:

```
sudo apt update
sudo apt install python3
```

* **Fedora**: выполните следующие команды в терминале:

```
sudo dnf update
sudo dnf install python3
```

* **Arch Linux и Manjaro**: выполните следующие команды в терминале:

```
sudo pacman -Syu
sudo pacman -S python
```

#### На macOS

1. Перейдите на официальный сайт Python по [адресу](https://www.python.org/downloads/mac-osx/).
2. Выберите нужную версию Python и скачайте установочный файл.
3. Запустите установочный файл и следуйте инструкциям мастера установки.
4. После завершения установки откройте терминал и введите `python3 --version`. Вы увидите версию установленного Python.

#### На Windows

1. Перейдите на официальный сайт Python по [адресу](https://www.python.org/downloads/windows/).
2. Выберите нужную версию Python и скачайте установочный файл.
3. Запустите установочный файл и следуйте инструкциям мастера установки.
4. После завершения установки откройте командную строку (cmd) и введите `python --version` или `python3 --version`. Если все сделано правильно, вы увидите версию установленного Python.

### Установка необходимых библиотек

#### Для работы этой программы необходимы следующие библиотеки Python:

1. `smtplib`: модуль для работы с серверами SMTP.
2. `getpass`: модуль для считывания пароля без экранирования.
3. `email.mime.text`: модуль для создания сообщений с текстовым контентом.
4. `csv`: модуль для считывания данных из файла CSV.
5. `sys`: модуль для управления стандартными потоками вывода и ошибок.

#### Для установки этих библиотек на разных операционных системах, используйте следующие команды:

* На Linux и macOS:

```
pip3 install smtplib getpass email csv
```

* На Windows:

```
pip install smtplib getpass email csv
```

После установки Python и необходимых библиотек, вы сможете запустить программу на разных операционных системах.

### Получение пароля

#### Шаг 1. Настройте ящик

1. Откройте [раздел «Почтовые программы»](https://mail.yandex.ru/?dpda=yes#setup/client) в настройках Яндекс Почты.
2. Обязательно выберите опции Разрешить доступ к почтовому ящику с помощью почтовых клиентов → С сервера imap.yandex.ru по протоколу IMAP и Пароли приложений и OAuth-токены.
3. Сохраните изменения.

#### Шаг 2. Создайте пароль приложения

1. Откройте страницу [Пароли приложений](https://id.yandex.ru/profile/apppasswords-list) вашего аккаунта Яндекс ID и нажмите Создать новый пароль.
2. Выберите тип приложения Почта.
3. Придумайте название пароля, например укажите название приложения, для которого вы создаете пароль. С этим названием пароль будет отображаться в списке.
4. Нажмите кнопку Далее. Пароль приложения отобразится во всплывающем окне.

### Пример использования

Для использования этой программы вам потребуется txt-файл `my_email.txt`, содержащий две строки: адрес электронной почты отправителя и пароль. ([Как получить пароль?](./#poluchenie-parolya))

#### Пример содержимого txt-файла:

```markup
example@yandex.ru
iluGyufvyufly
```

Файл `таблица.csv` должен содержать два столбца: адрес электронной почты получателя и текст сообщения. Каждая строка в файле представляет отдельное сообщение. Разделителем столбцов в файле должен быть символ `;`.

#### Пример содержимого CSV-файла:

```markup
john@example.com;Hello John, this is a test message.
jane@example.com;Hello Jane, this is a test message.

```

После запуска программы она прочитает этот файл, создаст два сообщения и отправит их на соответствующие адреса электронной почты.

Эта программа записывает информацию о каждом отправленном сообщении в файл `output.txt`. Информация включает в себя следующие детали:

* Техническую информацию.
* Отправителя сообщения.
* Получателя сообщения.
* Содержимое сообщения.

#### Вот пример того, что может быть записано в файл `output.txt`:

```markup
. . . # техническая информация
----------------------------------
Sender: your_email@example.com
----------------------------------
Recipient: recipient@example.com
----------------------------------
Email Content: Hello, this is a test message.
##################################
```

Этот формат повторяется для каждого сообщения, которое отправляется программой.

### Заключение

Эта программа представляет собой простой и эффективный инструмент для автоматизации отправки электронной почты из Python. Она может быть полезна в различных сценариях, таких как отправка уведомлений, рассылки или любых других задач, которые требуют автоматической отправки электронной почты.

***

#### **Более подробно про SMTP можно почитать** [**здесь**](http://codius.ru/articles/Python\_%D0%9A%D0%B0%D0%BA\_%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D1%82%D1%8C\_%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%BE\_%D0%BD%D0%B0\_%D1%8D%D0%BB%D0%B5%D0%BA%D1%82%D1%80%D0%BE%D0%BD%D0%BD%D1%83%D1%8E\_%D0%BF%D0%BE%D1%87%D1%82%D1%83)**.**
