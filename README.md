SPbU Discrete — Листки по дискретной математике

Назначение
- Репозиторий с заданиями и решениями в LaTeX.
- Каждый листок — отдельная папка `hometaskN` со своим `listN.tex` и собранным `listN.pdf`.

Структура Репозитория
- `hometask1/` — пример: исходник `list1.tex`, результат `list1.pdf`.
- `.gitignore` — игнор LaTeX‑артефактов.
- `README.md` — как работать, как сдавать.

Требования
- Установленный LaTeX: TeX Live (Linux), MacTeX (macOS) или MiKTeX (Windows).
- Утилита `latexmk` (обычно ставится вместе с TeX Live/MacTeX; в MiKTeX включите автоматическую установку пакетов).
- По желанию: VS Code + расширение LaTeX Workshop или любой другой редактор.

Установка latexmk (если не найден)
- macOS: установите MacTeX с сайта tug.org или `brew install --cask mactex-no-gui` (и затем `sudo tlmgr install latexmk`).
- Linux (TeX Live): установите пакет `latexmk` через менеджер пакетов (`apt install latexmk`, `dnf install latexmk`, и т. п.).
- Windows: установите MiKTeX, включите «Install missing packages on-the-fly».

Сборка PDF
- Одноразовая сборка: `latexmk -pdf hometask1/list1.tex`
- Непрерывная сборка при изменениях: `latexmk -pdf -pvc hometask1/list1.tex`
- Очистка временных файлов: `latexmk -C hometask1/list1.tex`

Правила Именования
- Папки: `hometaskN` (без пробелов), где `N` — номер листка.
- Файлы: `listN.tex` и итоговый `listN.pdf` в той же папке.

Инструкция Для Студентов: Форк и Сдача
1) Сделайте форк репозитория у себя на GitHub.
2) Клонируйте СВОЙ форк: `git clone <URL-вашего-форка>` и перейдите в папку проекта.
3) Создайте папку для нужного листка (если её нет), напр.: `hometask2/`.
4) Создайте исходник LaTeX `list2.tex` в этой папке. Минимальный шаблон:
   
   ```tex
   \documentclass[10pt]{article}
   \usepackage[utf8]{inputenc}
   \usepackage[T2A]{fontenc}
   \usepackage[russian]{babel}
   \usepackage{amsmath,amssymb,amsthm}
   \usepackage{hyperref}
   \title{Дискретная математика — Листок 2}
   \author{ФИО, группа}
   \date{\\Дата сдачи}
   \begin{document}
   \maketitle
   % Задача 1
   % Ваше решение
   \end{document}
   ```

5) Соберите PDF: `latexmk -pdf hometask2/list2.tex` → получите `hometask2/list2.pdf`.
6) Проверьте, что всё корректно отображается (формулы, кириллица, гиперссылки/оглавление).
7) Зафиксируйте изменения и отправьте в свой форк:
   - `git add hometask2/list2.tex hometask2/list2.pdf`
   - `git commit -m "Solve hometask 2"`
   - `git push`
8) Сдача: отправьте ссылку на ваш форк или создайте Pull Request в исходный репозиторий (если так указано преподавателем).

Чек‑лист Перед Отправкой
- PDF собирается без ошибок и предупреждений, влияющих на разметку.
- В репозитории нет временных LaTeX‑файлов (они игнорируются `.gitignore`).
- В коммите присутствуют только необходимые `.tex` и финальные `.pdf`.
- Имена папок/файлов без пробелов и соответствуют формату `hometaskN/listN.*`.

Подсказки и Частые Проблемы
- `latexmk: command not found` — установите `latexmk`/TeX Live/MacTeX/MiKTeX (см. раздел выше).
- Предупреждение про `todonotes` и `\marginparwidth` — добавьте в преамбулу перед `\usepackage{todonotes}` строку `\setlength{\marginparwidth}{2cm}`.
- Кириллица/кодировки — подключите в преамбуле:
  - `\usepackage[utf8]{inputenc}`
  - `\usepackage[T2A]{fontenc}`
  - `\usepackage[russian]{babel}`

Шпаргалка по Git
- Добавить файлы: `git add <путь>`
- Коммит: `git commit -m "сообщение"`
- Пуш: `git push`
- Забрать изменения из исходного репо в свой форк (по желанию):
  - Настройте upstream: `git remote add upstream <URL-исходного-репо>`
  - Обновите ветку: `git fetch upstream && git merge upstream/main`

Ссылки
- TeX Live: https://www.tug.org/texlive/
- MacTeX: https://tug.org/mactex/
- MiKTeX: https://miktex.org/
