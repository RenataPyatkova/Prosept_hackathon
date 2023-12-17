# Prosept_hackathon

Prosept. Cоздание сервиса для полуавтоматической разметки товаров.

Задача: разработка решения, которое автоматизирует процесс сопоставления товаров заказчика с размещаемыми товарами дилеров.

Использованный язык программирования - python.

Описание решения

За основную гипотезу выбрано предположение о том, что названий товаров достаточно для получения мэтча с приемлемой точностью. Для реализации проверки этой гипотезы выбран метод cosine_similarity, применённый к векторам названий, полученным с помощью TfidfVectorizer() и SentenceTransformer('LaBSE'). Сопоставляются вектора столбцов df_dealerprice.product_name и df_product.name. Остальные фичи не используются, так по итогам проверки гипотезы получен удовлетворительный результат.

Результаты

Выбранная базовая гипотеза подтвердилась, предложенные для её реализации методы TfidfVectorizer и SentenceTransformer('LaBSE'), применённые к векторам столбцов df_dealerprice.product_name и df_product.name, дали отличные результаты. При этом в используемых названиях от заказчика и дилеров всё еще есть недостатки. Некоторые недостатки, такие как отсуствие пробелов между словами, можно ликвидировать вручню, корректируя ошибки в данных. Однако такие недостатки как слишком некорретное описание товара у диллера исправить непредставляется возможным. 

В ходе выполнения проекта релизована предобработка данных. Разработан метод сопоставления топ n названий заказчиков названиям дилеров с применением ранжирования по cosine_similarity. Получены отличная скорость выполнения кода и отличное значение метрик. В финальном варианте выбор пал на TfidfVectorizer, выдающий 86% правильных названий в топ-5 и выполняющийся менее, чем за 1 секунду, так как он показал быструю работу и в связи с простотой библиотек представляет наиболее лёгкиё и надёжный вариант.
