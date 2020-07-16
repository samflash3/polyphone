Рассмотрим главный элемент редактора — дерево.
Оно отражает архитектуру открытого SoundFont; если щёлкнуть по тому или иному элементу в дереве, то в правой части программы откроется подходящий редактор.

Дальше познакомимся со [структурой дерева](#doc_structure), [контекстным меню](#doc_menu), [перетаскиванием](#doc_dragdrop), [копированием, вставкой ](#doc_copypaste) и [поиском](#doc_search) элементов.


## Структура {#doc_structure}


Структура дерева состоит из четырёх частей с заголовками :guilabel:`Общее`, :guilabel:`Семплы`, :guilabel:`Инструменты` и :guilabel:`Пресеты` и внутреннего содержания под этими заголовками.


![Дерево: структура](images/tree_1.png "Дерево: структура")


### Заголовок «Общее»


Щелчок по заголовку :guilabel:`Общее` открывает редактор [общей информации](manual/soundfont-editor/editing-pages/editing-of-the-general-information.md).


### Раздел «Семплы»


В этом разделе перечисляются семплы — исходный материал, из которого строятся инструменты.
Щелчок по одному или нескольким семплам открывает [редактор семплов](manual/soundfont-editor/editing-pages/sample-editor.md).
Щелчок по заголовку :guilabel:`Семплы` отображает [сводную информацию](manual/soundfont-editor/configuration-summaries.md#doc_sample) о настройках семплов.


### Раздел «Инструменты»


В этом разделе перечисляются инструменты — промежуточные элементы, которые создаются из семплов и используются в пресетах.
Инструменты содержат ссылки на семплы — «разделы», которые отображаются в виде списка под каждым инструментом.
Щелчок по инструменту или по разделу инструмента открывает [редактор инструмента](manual/soundfont-editor/editing-pages/instrument-editor.md).
Щелчок по заголовку :guilabel:`Инструменты` отображает [сводную информацию](manual/soundfont-editor/configuration-summaries.md#doc_instrument) о настройках инструментов.


### Раздел «Пресеты»


В этом разделе перечисляются пресеты — итоговые элементы, которые создаются из инструментов и доступны извне SoundFont.
Пресеты содержат ссылки на инструменты — «разделы», которые отображаются в виде списка под каждым пресетом.
Щелчок по пресету или разделу пресета открывает [редактор пресетов](manual/soundfont-editor/editing-pages/preset-editor.md).
Щелчок по заголовку :guilabel:`Пресеты` отображает [сводную информацию](manual/soundfont-editor/configuration-summaries.md#doc_preset) о настройках пресетов.


## Контекстное меню {#doc_menu}


Щелчок правой кнопкой мыши по элементу показывает меню:

Связать с…
: Связать выбранные семплы с инструментом; связать выбранные инструменты с пресетом.

Заменить на…
: Заменить семпл другим семплом в инструменте; заменить инструмент другим инструментом в пресете.
  Настройка семпла или инструмента при этом сохраняется.

Копировать
: Копировать выбранные элементы; сочетание клавиш :kbd:`Ctrl`+:kbd:`C`.

Вставить
: Вставить скопированные элементы; сочетание клавиш :kbd:`Ctrl`+:kbd:`V`.

Дублировать
: Дублировать выбранные элементы: семплы, инструменты, пресеты или разделы;
  сочетание клавиш :kbd:`Ctrl`+:kbd:`D`.

Удалить
: Удалить выбранные элементы; клавиша :kbd:`Del`.

Переименовать или Массовое переименование
: Переименовать выбранные элементы; клавиша :kbd:`F2`.
  Варианты массового переименования:
  
  * добавить в старое имя суффикс в виде имени клавиши — только для семплов,
  * заменить старое имя на числовой суффикс по возрастанию,
  * заменить символы,
  * вставить текст в указанной позиции,
  * удалить диапазон символов.


![Дерево: контекстное меню](images/tree_2.png "Дерево: контекстное меню")


## Перетаскивание {#doc_dragdrop}


Перетаскивание элементов в дереве помогает быстро связывать и копировать.
Чтобы перетащить несколько элементов, выделите их щелчком с клавишей :kbd:`Ctrl` или :kbd:`Shift`.

Результат перетаскивания зависит как от типа исходных элементов, так и от типа целевого элемента.

Семпл → инструмент
: Ассоциировать семпл с инструментом, создать раздел инструмента.

Семпл → заголовок :guilabel:`Инструменты`
: Создать один инструмент, который будет содержать перетаскиваемые семплы, либо создать отдельные инструменты для каждого перетаскиваемого семпла.

Инструмент → пресет
: Ассоциировать инструмент с пресетом, создать раздел пресета.

Инструмент → инструмент
: Копировать разделы исходного инструмента в целевой инструмент (в другой или тот же инструмент).

Раздел инструмента → инструмент или раздел инструмента
: Копировать раздел исходного инструмента в целевой инструмент (в другой или тот же инструмент).

Инструмент → заголовок :guilabel:`Пресеты`
: Создать один пресет, который будет содержать перетаскиваемые инструменты, либо создать отдельные пресеты для каждого перетаскиваемого инструмента.

Пресет → пресет
: Копировать разделы исходного пресета в целевой пресет (или в один и тот же пресет).

Раздел пресета → пресет или раздел пресета
: Копировать раздел исходного пресета в целевой пресет (или в один и тот же пресет).


## Копирование и вставка {#doc_copypaste}


Вместо перетаскивания элементов можно их скопировать и вставить.
Тот же результат достигается нажатием :kbd:`Ctrl`+:kbd:`C` и :kbd:`Ctrl`+:kbd:`V` в дереве.

Копирование и вставка так же работает между двумя SoundFont.
Элемент копируется из одного SoundFont вставляется в другой.
Выбирать можно и несколько элементов.

Выбраны семплы
: Копируются семплы.

Выбраны инструменты
: Копируются инструменты и связанные семплы.

Выбраны пресеты
: Копируются пресеты и связанные инструменты и семплы.

Если элементы копируются между двумя SoundFont и элемент с таким именем уже имеется, предоставляются варианты:

* игнорировать операцию, в этом случае элемент, имя которого совпадает, пропускается,
* заменить элемент, в этом случае старый элемент заменяется новым,
* дублировать элемент, в этом случае новый элемент копируется под другим именем рядом со старым.


## Поиск {#doc_search}


Чтобы упростить поиск элементов в дереве, панель поиска предоставляет фильтр.


![Дерево: поиск](images/tree_3.png "Дерево: поиск")


Если в поле поиска ввести строку, отобразятся только те элементы, которые её содержат.
Кроме того:

* если строка входит в название семпла — отображаются инструменты, которые используют этот семпл, и пресеты, которые используют эти инструменты,
* если строка входит в название инструмента — отображаются семплы, которые входят в этот инструмент, и пресеты, которые используют этот инструмент,
* если строка входит в название пресета — отображаются инструменты, которые входят в этот пресет, и семплы, которые входят в эти инструменты.

Фильтр отключается щелчком по крестику справа в поле ввода.