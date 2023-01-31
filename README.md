# Машинное обучение в бизнесе
![MarkDown](https://github.com/vit050587/ML_in_work/blob/master/tdsp-lifecycle2.png)
# Итоговый проект курса "Машинное обучение в бизнесе"
Данные: [Соревнования Kaggle](https://www.kaggle.com/datasets/andrewmvd/trip-advisor-hotel-reviews)
Задача: Классифицировать отзыв об отеле на TripAdvisor по его содержанию. Бинарная классификация

Используемые признаки:
**Review (text)**
Преобразования признаков: tfidf
Модель: **logreg**

##Клонируем репозиторий и создаем образ

$ git clone https://github.com/vit050587/ML_in_work/tree/master/Project.git
$ cd ML_in_work/tree/master/Project
$ docker build -t vit050587/review-sentiment-predict .

##Запускаем контейнер
Здесь Вам нужно создать каталог локально и сохранить туда предобученную 
[модель(распаковать архив)](https://github.com/vit050587/ML_in_work/blob/master/Project/model.zip) (<your_local_path_to_pretrained_models> 
нужно заменить на полный путь к этому каталогу)

$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models vit050587/review-sentiment-predict

##Переходим на [localhost:8181](http://localhost:8181/)

