# MANUAL_1C

[ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ](#первичное-создание-репозитория)
[ШАГ 1, ПЕРЕХОД В РАБОЧИЙ КАТАЛОГ](# ШАГ-1-ПЕРЕХОД-В-РАБОЧИЙ-КАТАЛОГ-(ЕСЛИ-репозиторий-ОТСУТСТВУЕТ-на-нашем-локальном-компьютере))


# ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ

1. Создал репозиторий       "X" на удаленном сервере github
2. Открываем консоль и выполняем команды:
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория
    git init
3. Создаем в корневом каталОге проекта, файл .gitignore
4. В файл gitignore добавляем: ConfigDumpInfo.xml

5. Создаем РЕЗЕРВНУЮ копию и работаем в дальнейшем с ней
6. Открываем конфигурацию    "Х" (или открыл обк "Х") в РЕЗЕРВНОЙ копии
7. Выполнил команду "Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"
    где каталОг для выгружаемых файлов это ЛокальныйКаталогКлонированыйРепозиторий
8. Открываем консоль и выполняем команды:
    git add .
    git commit -m "init nameObj_X"
    git push -u origin main // где main - это имя первичной ветки.

# ШАГ 1, ПЕРЕХОД В РАБОЧИЙ КАТАЛОГ (ЕСЛИ репозиторий ОТСУТСТВУЕТ на нашем локальном компьютере)

1. Открываем консоль и выполняем команды:
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория

# ШАГ 1, ПЕРЕХОД В РАБОЧИЙ КАТАЛОГ (ЕСЛИ репозиторий СУЩЕСТВУЕТ на нашем локальном компьютере)

1. Открываем консоль и выполняем команды:
    cd ПутьГдеХранитсяКаталог_Х_СПроектом
    git pull httpsRepositoryPath

# ШАГ 2, ПЕРЕД ВНЕСЕНИЕМ ЛЮБЫХ ИЗМЕНЕНИЙ (актуализируем данные)

1. Добавляем ветку   git branch   update_20220304_01
2. Переходим в ветку git checkout update_20220304_01
2. Открываем конфигурацию    "Х" (или открыл обк "Х") с актуальными данными (РАБОЧАЯ база)
3. Выполнил команду "Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"
    где каталОг для выгружаемых файлов это ЛокальныйРепозиторийПроекта
    (сохраняем с заменой текущих файлов). Командой git status можно увидеть изменения

4. git add .
5. git commit -m "update_20220304_01"
6. git push -u origin update_20220304_01

# СЛИЯНИЕ ВЕТОК (вливаем в главную ветку данные ветки с новыми данными)

1. Переходим на принимающую ветку git checkout main // где main - это  прин. ветка
2. Выполните команду git fetch, чтобы получить из него последние коммиты
3. Затем убедитесь, что в ветке main также содержатся последние изменения git pull
4. git merge update_20220304_01 // где "update_20220304_01" - это название ветки-источник

5. git commit -m "merge update_20220304_01"
6. git push -u origin main // где main - это имя первичной ветки.

7. Удаляем вспомогательную ветку созданную для актуализации данных: git branch -d update_20220304_01

# ШАГ 3, ИЗМЕНЕНИЯ ДАННЫХ (ВСЕГДА В НОВОЙ ВЕТКИ!)

1. Создаем ветку для выполнения "задачи": git branch ITTF_01
2. Переходим на ветку задачи: git checkout ITTF_01
3. Проверяем переход: git branch

4. Открываем конфигурацию    "Х" (или открыл обк "Х") (РЕЗЕРВНУЮ копию)

5. Вносим изменения
6. Выполнил команду "Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"
7. git add .
8. git status
9. git commit -m "some comment"
10. Повторяем с шага №5

(11. Когда захотим выгрузить ветку на удаленный сервер: git push -u origin ITTF_01 (пункт 4))

(12. КОГДА ЗАДАЧА БУДЕТ ГОТОВА - выполняем ШАГ №2, после чего "СЛИЯНИЕ ВЕТОК" main с ITTF_01)

# Добплнительно:
    На удаленный сервер выгружаются из локального репозитория ИСКЛЮЧИТЕЛЬНО
    те ветки из которых была выполнена команда push. Что бы выгрузить две
    ветки необходимо в каждой из них выполнить команду push
    (иначе ветка останется исключительно в текущем локальном репозитории)
