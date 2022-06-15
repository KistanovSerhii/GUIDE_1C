##### <a name="pageup"></a>



# Разделы

+ [ШАГ 0, ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ](#Step0); ➕
+ [ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) СУЩЕСТВУЕТ на этом ПК](#Step1_1);  🟣
+ [ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) ОТСУТСТВУЕТ на этом ПК](#Step1_2); 🔘
+ [ШАГ 2, СОЗДАЕМ И ВЫПОЛНЯЕМ задачу](#Step2); 🪚


+ [ШАГ 3, ПЕРЕНОСИМ ИЗМЕНЕНИЯ (задачи в ветку копии)](#Step3);  🚡

+ [ШАГ 4, ВНЕДРЕНИЕ С КОНФЛИКТОМ](#Step4); 🏁

+ [ШАГ 5, ВНЕДРЕНИЕ когда НЕТ КОНФЛИКТОВ](#Step5);      🛰️

+ [ПРОСТО КОМАНДЫ](#Step6); ⚛️




_Схема разработки:_
+ Ветка main всегда содержит исключительно актуальную (рабочую) версию!
+ Любые задачи должны выполнятся в копии, по этому для нее создается ветка copy_xxxxxxxx_xx
+ Для каждой задачи должна создаватся ветке (ITTF_01) от ветки (копии)
+ Задача завершается слиянием ветки задачи (ITTF_01)  с веткой копии
+ Перед внедрением необходимо обновить ветку main до актуальной версии
+ Внедрение задачи завершается слиянием ветки копии с веткой main

+ _Обновление рабочих данных можно одним из двух способов (Загрузка из файлов ИЛИ Сравнить и объединить)_ 🏁


##### <a name="Step0"></a> ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ [(начало)](#pageup);

# ПЕРВИЧНОЕ СОЗДАНИЕ РЕПОЗИТОРИЯ ➕

1. **Создаем репозиторий** "X" на удаленном сервере github с добавлением файлов:

        .gitignore (template Scheme)
        README.md

2. Редактируем файл .gitignore: 
        
        Очищаем текущее содержимое
        Добавляем ConfigDumpInfo.xml
        Сохраняем

3. _Открываем консоль (на локальном ПК) и выполняем команды:_
#    
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория

4. Создаем актуальную _РЕЗЕРВНУЮ копию_ (далее работаем исключительно с этой копией)
5. Открываем конфигуратор актуальную _РЕЗЕРВНУЮ копию_
6. Выполнил команду **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**

        где каталОг для выгружаемых файлов это ЛокальныйКаталог-КлонированыйРепозиторий

7. Открываем консоль и выполняем команды:
#
    git add .
    git commit -m "init 1.0.1"
    git push -u origin main
    
   _// где main - это имя первичной ветки_
   
   Таким образом мы создаем бессрочный репозиторий с веткой main
   в которой будет исключительно актуальная (рабочая) версия обк!




##### <a name="Step1_1"></a> ШАГ 1 [(начало)](#pageup);

# ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **СУЩЕСТВУЕТ** на этом ПК 🟣


1. Открываем консоль и выполняем команды:
#
    cd КорневойКаталОг_Х_Проекта
    git pull httpsRepositoryPath




##### <a name="Step1_2"></a> ШАГ 1 [(начало)](#pageup);

# ШАГ 1, Начало работы КОГДА РЕПОЗИТОРИЙ (проект) **ОТСУТСТВУЕТ** на этом ПК 🔘


1. Открываем консоль и выполняем команды:
#
    cd ПутьГдеБудемХранитьКаталог_Х_СПроектом
    git clone httpsRepositoryPath
    cd ИмяКлонированногоРепозитория




##### <a name="Step2"></a> ШАГ 2 [(начало)](#pageup);

# ШАГ 2, СОЗДАЕМ И ВЫПОЛНЯЕМ задачу 🪚

+ 🤷‍ ПЕРЕД созданием задачи:
1. _Если ветка копии существует Тогда ВЫБИРАЕМ ЕЕ_ 🤷‍♂️ 
        
        git checkout copy_xxxxxxxx_xx
        
2. _Иначе СОЗДАЕМ ветку копии и сразу ВЫБИРАЕМ ЕЕ_ 🤷‍ 
        
        git checkout -b copy_xxxxxxxx_xx

3. Выгружаем на удаленный репозиторий 
        
        git push -u origin copy_xxxxxxxx_xx




+ 🐤 СОЗДАНИЕ задачи:

1. Создаем для задачи ветку _(В ВЕТКЕ copy_xxxxxxxx_xx для этого сначала надо перейти на ветку копии)_
        
        git branch ITTF_01
        
2. Переходим на ветку задачи:
    
        git checkout ITTF_01
        
3. Проверяем переход:

        git branch



##### <a name="Step2_3"></a>

+ РАБОТА НАД ЗАДАЧЕЙ: 🛠️

1. Открываем конфигурацию "Х" (или открыл обк "Х") _(в РЕЗЕРВНОЙ копии)_
2. 🩹 Вносим изменения

_Первое изменение которое можно внести и зафиксировать - это смена версии (обработки) "x.x.x.1"_

_Когда решили что пора сохранить изменения в сис. контроля версий ЛОКАЛЬНО:_ ◘

3. Выполнил команду   **"Выгрузить конфигурацию в файлы"/"Выгрузить в файлы"**

_выгружаем с заменой текущих файлов (перезаписываем, обязательно при этом должна быть выбрана ветка задачи!)_
#
    git add .
    git status
    git commit -m "some comment"

  **Повторяем с шага №2** 🩹


_Когда решили что пора сохранить изменения в сис. контроля версий УДАЛЕННО_ ✔️
#   
    git push -u origin ITTF_01




##### <a name="Step3"></a> ШАГ 3 [(начало)](#pageup);

# ШАГ 3, ПЕРЕНОСИМ ИЗМЕНЕНИЯ _(задачи в ветку копии)_ 🚡


1. Переходим на ветку копии: git checkout copy_xxxxxxxx_xx
2. Выполняем слияние ветки копия с веткой задачи: git merge ITTF_01

_По необходимости коммитим и пушим на удаленный сервер ветку copy_xxxxxxxx_xx_




##### <a name="Step4"></a> ШАГ 4 [(начало)](#pageup);

# ШАГ 4, ВНЕДРЕНИЕ С КОНФЛИКТОМ: 🏁

1. Через конфигуратор выполнил сравнить и объединить (для устранения конфликтов)
    
        Если Конфликт Тогда
            ОБЪЕДИНЯЕМ (merge) ветку КОПИИ с веткой задач
            Удаляем ветки задач (git branch -d ITTF_xx)
            
            ОБЪЕДИНЯЕМ (merge) ветку main с веткой копии
            Удаляем ветки копии (git branch -d copy_xxxxxxxx_xx)
            
            РЕШАЕМ конфликт через конфигуратор (оставляем нужное и удаляем не нужное)
            Результатом решения конфликта через конфигуратор будет новая версия обк!

            Новый обк готов заменить текущий рабочий обк!
            
            АКТУАЛИЗИРУЕМ данные (добавлением нового обк) в сис. контроля версий
            git fetch
            git pull
            
            "Выгружаем в файлы" новую версию (которая получилась после решения конфликта)
            в репозиторий текущего проекта (в единственную ветку main)
            
            git add .
            git commit -m "ITFC_xxxxxxxx_xx"
            git push -u origin main
        ИНАЧЕ
            ВЫПОЛНЯЕМ ШАГ 5 (ВНЕДРЕНИЕ БЕЗ КОНФЛИКТОВ 🛰️)
            
            


##### <a name="Step5"></a> ШАГ 5 [(начало)](#pageup);

# ШАГ 5, ВНЕДРЕНИЕ когда НЕТ КОНФЛИКТОВ 🛰️

        ОБЪЕДИНЯЕМ (git merge ITTF_xx) ветку КОПИИ с веткой задач
        Удаляем ветки задач (git branch -d ITTF_xx)
        
        АКТУАЛИЗИРУЕМ данные ветки main
        git checkout main
        git fetch
        git pull
        
        "Выгружаем в файлы" новую версию объекта НЕ имеющую конфликтов
        в репозиторий текущего проекта (в ветку main)
        
        ФИКСИРУЕМ актуализацию данных
        git add .
        git commit -m "update to current data"
        git push -u origin main
        
        ОБЪЕДИНЯЕМ (git merge copy_xxxxxxxx_xx) ветку MAIN с веткой КОПИИ
        Удаляем ветки КОПИИ (git branch -d copy_xxxxxxxx_xx)
        
        ПОВТОРЯЕМ "ФИКСИРУЕМ актуализацию данных", НО message "implementation ITTF_01_ITTF_02"
        через нижнее подчеркивание перечисляем какие задачи внедрены.



##### <a name="Step6"></a> [(начало)](#pageup);

# ПРОСТО КОМАНДЫ ⚛️

ПЕРЕД Объединением:

    git checkout main    
    git fetch
    git pull

ОБЪЕДИНЕНИЕ веток: 
       
    git merge ИмяВеткиИСТОЧНИК

УДАЛЕНИЕ ветки: 🙈

        git branch -d copy_xxxxxxxx_xx

Authentication Failed:

       git remote -v
       git remote set-url origin git@github.com:USERNAME/REPONAME.git
       // git@github.com:USERNAME/REPONAME.git - это ссылка на текущий репозиторий
       // (git remote set-url origin https://github.com/KistanovSerhii/PROF1S.git)
       // Как правило после этого надо сделать git fetch, git pull, выгрузить в файлы из 1С


# Добплнительно:
    На удаленный сервер выгружаются из локального репозитория ИСКЛЮЧИТЕЛЬНО
    те ветки из которых была выполнена команда push. Что бы выгрузить две
    ветки необходимо в каждой из них выполнить команду push
    (иначе ветка останется исключительно в текущем локальном репозитории)
    
    С какой ветки выполняется команда создать новую ветку - с той ветки
    начинается новое ответвление (копируется именно та ветка С которой выполнена команда!)
    
    Если игнорируемый файл попал в индекс не смотря на **.gitignore** и нужно убрать его из индекса:
    git rm --cached path/to/file
    
    После push (особенно main ветки) лучше убедится что push выполнился,
    а то у меня была ситуация что commit остался в локальном репозитории! 🤡



[(начало)](#pageup);
