## Работа с удалённым репозиторием

Удалённый репозиторий хранится на GitHub или другом Git-сервисе.

---

### Добавление удалённого репозитория

Команда связывает локальный репозиторий с удалённым.

git remote add origin ссылка_на_репозиторий

Пример:

git remote add origin https://github.com/username/git-instruction.git

---

### Проверка удалённого репозитория

Команда показывает список подключённых удалённых репозиториев.

git remote -v

---

### Удаление удалённого репозитория

git remote remove origin

---

### Отправка изменений на GitHub

Команда отправляет локальные коммиты в удалённый репозиторий.

git push origin имя_ветки

Пример:

git push origin main

---

### Первая отправка ветки

Команда отправляет ветку и связывает её с удалённой веткой.

git push -u origin имя_ветки

Пример:

git push -u origin main

После этого можно писать просто git push.

---

### Получение изменений из удалённого репозитория

Команда скачивает изменения и сразу объединяет их с текущей веткой.

git pull origin имя_ветки

Пример:

git pull origin main

---

### Загрузка изменений без слияния

Команда скачивает информацию об изменениях, но не объединяет их автоматически.

git fetch

git fetch --all

---

### Клонирование репозитория

Команда создаёт локальную копию удалённого репозитория.

git clone ссылка_на_репозиторий

Пример:

git clone https://github.com/username/git-instruction.git

---

### Удаление ветки на удалённом репозитории

git push origin --delete branch-name

---

### Работа с тегами

Создание тега:

git tag v1.0

Создание тега с описанием:

git tag -a v1.0 -m "Релиз версии 1.0"

Отправка тегов на GitHub:

git push --tags

---

## Работа с форками

**Fork** — это копия чужого репозитория в вашем аккаунте GitHub.

Форки используются, когда нужно предложить изменения в чужой проект.

---

### Как сделать fork

1. Открыть чужой репозиторий на GitHub
2. Нажать кнопку **Fork**
3. GitHub создаст копию репозитория в вашем аккаунте

---

### Клонирование форка

git clone ссылка_на_форк

Пример:

git clone https://github.com/username/project-fork.git

---

### Добавление исходного репозитория

Команда добавляет оригинальный репозиторий как upstream.

git remote add upstream ссылка_на_исходный_репозиторий

Пример:

git remote add upstream https://github.com/original-owner/project.git

---

### Получение изменений из исходного репозитория

git fetch upstream

---

### Обновление своей ветки из upstream

git merge upstream/main

---

### Полный цикл работы с fork

1. Сделать fork репозитория на GitHub
2. Клонировать свой fork:

git clone https://github.com/username/repo.git
cd repo

3. Добавить upstream:

git remote add upstream https://github.com/original/repo.git

4. Создать ветку для изменений:

git branch my-changes
git switch my-changes

5. Внести изменения, закоммитить:

git add .
git commit -m "Мои изменения"

6. Отправить в свой fork:

git push -u origin my-changes

7. На GitHub нажать **New Pull Request**
8. Выбрать исходную и целевую ветки
9. Описать изменения и отправить

---

### Синхронизация fork с оригиналом

git fetch upstream
git checkout main
git merge upstream/main
git push origin main
