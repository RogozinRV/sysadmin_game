SYSADMIN SIMULATOR: 5/2 EDITION
===============================

В этой папке две части:

  Готовый_билд\   — игра для Windows, запускать сразу
      SysadminSimulator.exe   один файл, 22 МБ, установка и Python не нужны
      КАК_ЗАПУСТИТЬ.txt       запуск, сейвы, предупреждение SmartScreen, клавиши

  Исходники\      — всё, из чего собран билд
      sysadmin_game\          проект игры
          main.py             точка входа
          config.py           константы: окно, палитра, смена, баланс
          engine\             движок: окно, ASCII-рендер и CRT, время, звук,
                              почта, мир, ресурсы, Паша, кампания, ивенты, сейвы
          game_states\        экраны: ноутбук, карта, диалог, мини-игра,
                              итоги дня, выходные, финал, меню, настройки
          minigames\          15 мини-игр (easy / medium / hard / events)
          ui\                 кнопки, списки, рамки
          data\               все базы в .json: письма, сотрудники,
                              мини-игры, банк звуков, контакты
          assets\             шрифт PT Mono, 52 портрета, 32 звука, QR
          packaging\          рецепт сборки exe (spec, хук сейвов, .bat)
          README.md           правила, управление, звук, финал
          TODO.md             что сделано по шагам
          OPEN_QUESTIONS.md   принятые решения
          DESIGN_MAIL.md      раскладка писем месяца
          DESIGN_EVENTS.md    дизайн ивентов
          requirements.txt    pygame-ce >= 2.5.0
      portrait_tool.py        фото -> ASCII-портрет белыми символами
      portrait_faces.py       процедурные лица (старый вариант портретов)
      sound_build.py          выравнивание громкости эффектов
      music_synth.py          синтез фоновой музыки
      ambience_build.py       гул кафетерия

ЗАПУСК ИГРЫ
  Готовый_билд\SysadminSimulator.exe — двойной клик.
  Сейвы и настройки появятся рядом с exe в папке saves.

ЗАПУСК ИЗ ИСХОДНИКОВ
  cd Исходники\sysadmin_game
  python -m venv .venv
  .venv\Scripts\activate
  pip install -r requirements.txt
  python main.py

ПЕРЕСБОРКА EXE
  Исходники\sysadmin_game\packaging\build_windows.bat
  Готовый exe появится в Исходники\release — перенеси его в Готовый_билд.
  Подробности и грабли сборки: packaging\BUILD_WINDOWS.md.
