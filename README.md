# Пример озер данных (manifest)

**Цели примера:**
1. Снизить порог вхождения в DocHub за счет исследования полнофункционального работающего примера.
2. Показать пример структуры репозитория с данными
3. Показать примеры расширения дефолтной метамодели


# Суть примера
Существует множество различных подходов к описанию архитектуры компании. В нашей компании была выбрана методология TOGAF. При этом мы не пытаемся внедрить классическую методологию TOGAF, мы используем комбинированный подход, выбирая только те инструменты, которые закрывают наиболее критичные риски компании.

Согласно методологии TOGAF архитектура предприятия делится на 4 домена:

1. Бизнес-архитектура - описание бизнес-процессов компании
2. Информационная архитектура - описание архитектуры данных
3. Прикладная архитектура - описание архитектуры программных продуктов (системы, сервисы, приложения и т.д.)
4. Технологическая архитектура - описание архитектуры инфраструктуры

![TOGAF](./images/arch_approach.png)

Вся структура примера разработана под выбранную методологию с учетом нашего видения. В общем случае в данном репозитории мы ведем прикладную архитектур ровня ПА-L1, но если у системы нет своего репозитория, либо у архитектора несколько систем, то он может управлять в этом репозитории и уровнем ПА-L2.

## Файловая структура примера
**swamp**
    * **adr** - в этой папке хранится реестр архитектурных решений
    * **application_arch** - в этой папке хранятся все данные, связанные с прикладной архитектурой, кроме контекстов. Контексты мы вынесли в отдельную папку artifacts. Детально про artifacts можно почитать ниже.
        * **aspects** - в этой папке хранятся аспекты. В примере аспекты используются в качестве функционала системы.
        * **libraries** - в этой папке хранятся библиотеки компании.
        * **reports** - в этой папке хранятся различные отчеты по системам.
        * **systems** - в этой папке хранятся данные по системам. Каждую систему мы описываем либо в своём файле либо в отдельной папке в случае если по системе нужна дополнительная документация. Имя файла или папки всегда соответствует имени системы. Документацию описанию прикладной архитектуры вы сможете найти в самом примере: http://localhost:8080/entities/docs/blank?dh-doc-id=enterprise_arch.arch_desc_guide.    
        * **users** - в этой папке хранится список пользователей системы.
    * **artifacts** - в этой папке хранятся все артефакты по системам, например контексты. Также здесь можно хранить различные схемы по системам.
        * **common** - в этой папке хранится общий контекст ГК Болото.
        * **bu_<имя бизнес-юнита>** - в этой папке хранится контекст БЮ Лягушачий рай.
    * **business_arch** - в этой папке хранятся все данные, связанные с бизнес-архитектурой.
    * **dictionaries** - вспомогательная папка для хранения справочной информации. Кастомная сущность описанная в [репозитории](https://github.com/ValentinKozlov/DocHubExampleMetamodel).
    * **documentation** - в этой папке хранится общая документация.
        * **glossary** - в этой папке хранится глоссарий ГК Болото.
        * **intro** - в этой папке хранится информация о том, что такое архитектура ГК Болото.
        * **useful_links** - в этой папке хранятся полезные линки на внешние ресурсы.    
    * **enterprise_arch** - это папка корпоративных архитекторов, сюда можно поместить всю информацию, которая связана с развитием архитектуры в компании.    
        * **processes** - в этой папке хранится документацию по различным архитектурным процессам
        * **tools** - в этой папке хранится документация по инструментам архитектуры
            * **dochub** - в этой папке хранится документация по DocHub
        * **welcome** - в этой папке хранится документация, которая выводится при открытии DocHub (welcome page) 
    * **images** - картинки для настоящей документации
    * **information_arch** - в этой папке хранятся все данные, связанные с информационной архитектурой.
        * **business_entities** - в этой папке хранятся данные по бизнес-сущностям. Кастомная сущность описанная в [репозитории](https://github.com/ValentinKozlov/DocHubExampleMetamodel).
    * **metamodels** - в этой папке хранятся все метамодели, а также дополнительные наборы данных и инструментов необходимых для разработки метaмоделей и их валидации.
        * **custom** - в этой папке хранится описание всех пользовательских матамоделей.
            * **business_entities** - в этой папке хранится описание модели по управлению бизнес-сущностями на логическом уровне.
            * **dictionaries** - в этой папке хранится матамодель описывающая структуру справочников.
            * **dochub_menu** - в этой папке хранится матамодель описывающая целевую структуру меню.
        * **datasets** - в этой папке хранятся все общие запросы (datasets).
        * **default** -  в эту папку была перенесена метамодель DocHub заданная по умолчанию. Также  папке хранятся все инструменты для расширения дефолтных метамоделей DocHub.
            * **entities** - в этой папке хранится метамодель DocHub заданная по умолчанию.
            * **rules** - в этой папке хранится матамодель штатных валидаторов ядра, а также кастомных расширений. В самой папке есть два вида примеров, это валидация через schema и валидация через проверку заполнения конкретных параметров. Пример использования для schema можно посмотреть [здесь](https://github.com/rpiontik/DocHubExamples/tree/main/src/validator_example).
        * **jsonata** - в этой папке хранятся общие функции. Пример использования можно посмотреть [здесь](https://github.com/rpiontik/DocHubExamples/blob/main/src/jsonata_query_examples/jsonata_query_example.md).
    * **standards** - это одна из ключевых папок, где хранятся архитектурные принципы и стандарты, которые обязательны к выполнению всеми командами
        * **arch_principles** - здесь описаны архитектурные принципы и принципы информационной безопасности
        * **it_platforms** - здесь хранятся архитектурные стандарты по платформам, а также принятые нотации по кодированию
        * **patterns** - здесь описываются различные паттерны, которые могут использовать команды. В репозитории есть пример реализации одного из таких паттернов.
    * **tech_arch** - в этой папке хранятся все данные, связанные с технологической архитектурой. 
        * **environments** - в этой папке хранятся данные по средам развертывания. Кастомная сущность описанная в [репозитории](https://github.com/ValentinKozlov/DocHubExampleMetamodel).
        * **reports** - в этой папке хранятся отчеты по технической архитектуре
    * **dochub_menu.yaml** - файл со структурой меню. После того как Рома сделал возможность сортировать меню, то можно структуру меню сделать сразу при загрузке, а потом потихоньку его наполнять. Кастомная сущность описанная в [репозитории](https://github.com/ValentinKozlov/DocHubExampleMetamodel).
* **_root.yaml** - корневой файл для импорта
* **dochub.yaml** - корневой файл DocHub. Для того чтобы заработало в плагине, нужно извратиться и подключить кастомную метамодель.
* **README.md** - текущая документация

## Правила импорта yaml файлов
Импорт всех файлов делается только через `_root.yaml`. Это означает что при создании любой папки всегда нужно сначала добавлять `_root.yaml`, а уже внутри подключать файлы. Исключения составляет только подход с описанием систем.
Такой подход позволяет очень быстро переструктурировать папки репозитория, а также избегать множественного импорта при подключении репозитория как подмодуль.

## Использование
Самый простой способ запустить озеро данных - это воспользоваться репозиторием https://github.com/cu3blukekc/SwampHub.

Остальные способы вариативны и зависят от глубины понимания вами принципов работы DocHub.

## Авторские права
1. Данный репозиторий с примерами был выполнен Валентином Козловым https://t.me/i_frog_i.
2. В пример были включены наработки Романа Пионтика и участников сообщества, а именно:
    * Максима Муратова
    * Если кого-то забыл, прошу написать, я добавлю

В дальнейшем планируется собрать на базе этого репозитория все интересные наработки сообщества опубликованные [здесь](https://github.com/rpiontik/DocHubExamples).
