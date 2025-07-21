# Hugo Project - Руководство по настройке и использованию

## О проекте

Этот проект создан на основе статического генератора сайтов Hugo. Включает настраиваемые компоненты для карточек статей, блоков с отзывами и страницы "О компании".

## Требования

- Hugo (версия 0.101.0 или выше)
- Git (для управления версиями)

## Установка

1. Клонируйте репозиторий:

```bash
git clone https://github.com/shamalli/hugo-test.git
cd hugo-project
```

2. Установите тему (пример для Ananke):

```bash
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

3. Запустите сервер разработки:

```bash
hugo server -D
```

Структура проекта

```
├── assets/          # CSS/JS файлы
├── content/         # Контент сайта
├── data/            # Файлы данных (YAML/JSON)
├── layouts/         # Кастомные шаблоны
├── static/          # Статические файлы
├── themes/          # Установленные темы
└── hugo.toml      # Основной конфиг
```

# Основные компоненты
## 1. Карточки статей

Расположение:

```
layouts/partials/article-card.html
```

Использование:

Добавьте новую карточку в content/blog/, пример:

```
+++
date = '2025-07-18T21:09:23+06:00'
draft = false
title = 'Первая статья'
featured_image = '../uploads/Изображение.png'
summary = "Краткое описание"
+++
Content text
```

Использование в списках

---
    {{ range .Pages }}
        {{ partial "article-card" . }}
    {{ end }}
---

## 2. Блоки отзывов

Расположение:

    Шаблон: layouts/partials/testimonial.html

    Данные: data/testimonials.yaml

Добавление отзыва в data/testimonials.yaml:

```
- name: "Имя автора"
  position: "Должность"
  content: "Текст отзыва"
```

## 3. Страница "О компании"

```
Шаблон: layouts/_default/about.html
```

Настраиваемые параметры в content/about/_index.md:

```
+++
date = '2025-07-18T21:09:03+06:00'
draft = false
title = 'О компании'
featured_image = '../uploads/Изображение.png'
+++
Content text
```

## Источники

Hugo Official Docs - https://gohugo.io/documentation/

Support forum - https://discourse.gohugo.io/

Тема Ananke - https://themes.gohugo.io/themes/gohugo-theme-ananke/

Introduction to Hugo Templating - https://www.engino.co.uk/icons/introduction/

Hugo, the scope, the context and the dot - https://www.regisphilibert.com/blog/2018/02/hugo-the-scope-the-context-and-the-dot