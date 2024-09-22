# Документация по модели C4 

Этот репозиторий содержит исходники для `GitHub Pages`, сайта опубликованного по адресу [https://c4m.khramtsoft.ru](https://c4m.khramtsoft.ru)

## Локальная разработка

Если вы хотите создать / просмотреть документы локально:

1. `git clone https://github.com/andreykhr/c4model.git`
1. `cd c4model`
1. `docker run -p 4000:4000 -v $(pwd):/site bretfisher/jekyll-serve`
1. Open http://localhost:4000
