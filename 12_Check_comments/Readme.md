# Обучение модели классификации комментариев
Интернет-магазин запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.   

Обучить модель классифицировать комментарии на позитивные и негативные. Определение токсичности комментариев.

# Описание данных
Набор данных с разметкой о токсичности правок.  

# Выводы
- выявили значительную разбалансировку классов (9:1 отрицательного к положительному классу)
- обучили три модели: RandomForestClassifier, LGBMClassifier, LogisticRegression и константную модель с постоянным предсказанием класса 0, так как данный класс в 9 раз превышает класс 1
- с метрикой __f1_score__ наилучшим образом показала себя модель LogisticRegression, чуть хуже значение у модели LGBMClassifier
- на тестовой выборке результаты подтвердились, __f1_score__ почти не отличается от результатов на обучающей, что говорит о том, что модели не были переобучены
- наиболее предпочтительной выглядит модель LogisticRegression с наивысшим результатом полноты и точности