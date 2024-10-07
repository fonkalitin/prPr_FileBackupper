Модуль для Нанокад СПДС (nanoCAD SPDS). 
Данный модуль работает только в нанокад СПДС начиная с версии 24.0 т.к. только начиная с этой версии в API был добавлен метод .import("MCDI").

Модуль выполняет:
- проверку подключенной в данный момент БД (сетевая/локальная);
- автоматический импорт файлов MCDI.

Все настройки хранятся во внешнем конфиг-файле "prPr_DBConfig.ini" который должен быть расположен в одном каталоге вместе с *.dll.

- Настройка файла конфигурации "prPr_DBConfig.ini":
 
  [MCDI]
- MCDIfolderPath = D:\Soft\nCAD\MCDI\    # Путь где распологается импортируемый MCDI файл;
- MCDIfilename = TestObject.mcdi    # Имя импортируемого MCDI файла;
 
  [spdsDB]
- DBfolderName = _НАНО-ПРОЕКТ    # Наименование целевого каталога в базе элементов СПДС;
- importToRoot = false    # Импортировать MCDI файл непосредственно в корень базы элементов (да/нет - true/false);
- DBname = pgsql:localhost:nspds240    # Полное наименование Локальной БД элементов в которой у пользователя есть права на запись (этот путь будет предложен по умолчанию для переключения с сетевой БД);
 
  [options]
- autoUpdNeeded = true    # Флаг автообновления. Если включен (true) то при каждой загрузке нанокад будет выполняться импорт заданного MCDI (с перезаписью);
- silentMode = false    # Флаг тиходо режима, без уведомлений. Если включен (true) то при загрузке модуля не будет появляться окно с вопросом "Хотите Обновить БД?";
