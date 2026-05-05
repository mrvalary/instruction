## Работа с удалённым репозиторием

Удалённый репозиторий хранится на GitHub или другом Git-сервисе.

### Добавление удалённого репозитория

Команда связывает локальный репозиторий с удалённым.
``` bash
git remote add origin ссылка_на_репозиторий
```
Пример:
``` bash
git remote add origin https://github.com/username/git-instruction.git
```

### Проверка удалённого репозитория

Команда показывает список подключённых удалённых репозиториев.
``` bash
git remote -v
```

### Удаление удалённого репозитория
``` bash
git remote remove origin
```

### Отправка изменений на GitHub

Команда отправляет локальные коммиты в удалённый репозиторий.
``` bash
git push origin имя_ветки
```
Пример:
``` bash
git push origin main
```

### Первая отправка ветки

Команда отправляет ветку и связывает её с удалённой веткой.
``` bash
git push -u origin имя_ветки
```
Пример:
``` bash
git push -u origin main
```
После этого можно писать просто git push.

### Получение изменений из удалённого репозитория

Команда скачивает изменения и сразу объединяет их с текущей веткой.
``` bash
git pull origin имя_ветки
```
Пример:
``` bash
git pull origin main
```

### Загрузка изменений без слияния

Команда скачивает информацию об изменениях, но не объединяет их автоматически.
``` bash
git fetch
git fetch --all
```

### Клонирование репозитория

Команда создаёт локальную копию удалённого репозитория.
``` bash
git clone ссылка_на_репозиторий
```
Пример:
``` bash
git clone https://github.com/username/git-instruction.git
```

### Удаление ветки на удалённом репозитории
``` bash
git push origin --delete branch-name
```

### Работа с тегами

Создание тега:
``` bash
git tag v1.0
```
Создание тега с описанием:
``` bash
git tag -a v1.0 -m "Релиз версии 1.0"
```
Отправка тегов на GitHub:
``` bash
git push --tags
```

---
## Работа с форками

**Fork** — это копия чужого репозитория в вашем аккаунте GitHub.
Форки используются, когда нужно предложить изменения в чужой проект.

### Как сделать fork

1. Открыть чужой репозиторий на GitHub
2. Нажать кнопку **Fork**
3. GitHub создаст копию репозитория в вашем аккаунте

### Клонирование форка
``` bash
git clone ссылка_на_форк
```
Пример:
``` bash
git clone https://github.com/username/project-fork.git
```

### Добавление исходного репозитория

Команда добавляет оригинальный репозиторий как upstream.
``` bash
git remote add upstream ссылка_на_исходный_репозиторий
```
Пример:
``` bash
git remote add upstream https://github.com/original-owner/project.git
```

### Получение изменений из исходного репозитория
``` bash
git fetch upstream
```

### Обновление своей ветки из upstream
``` bash
git merge upstream/main
```

### Полный цикл работы с fork

1. Сделать fork репозитория на GitHub
2. Клонировать свой fork:
``` bash
git clone https://github.com/username/repo.git
cd repo
```
3. Добавить upstream:
``` bash
git remote add upstream https://github.com/original/repo.git
```
4. Создать ветку для изменений:
``` bash
git branch my-changes
git switch my-changes
```
5. Внести изменения, закоммитить:
``` bash
git add .
git commit -m "Мои изменения"
```
6. Отправить в свой fork:
``` bash
git push -u origin my-changes
```
7. На GitHub нажать **New Pull Request**
8. Выбрать исходную и целевую ветки
9. Описать изменения и отправить

### Синхронизация fork с оригиналом
``` bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```
