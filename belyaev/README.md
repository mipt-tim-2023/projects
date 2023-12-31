## Предсказание тегов по названию и описанию

Мой проект заключается в обучении нейросети для предсказания тегов стартапов
YC по их названию и описанию.

Это может быть использовано для выявления необычных проектов, для которых
предсказание значительно отличается от остальных. Вероятно, такие проекты
будут заслуживать особого внимания инвесторов.

_Беляев Андрей_

### Выводы - 13.12.2023
Наиболее популярные теги на YC слабо связаны с сутью стартапа, и, видимо,
зачастую ставятся ради повышения его заметности. Эти теги включают:

```
SaaS, B2B, Fintech, Developer Tools, Artificial Intelligence, Marketplace,
AI, Machine Learning, E-commerce, Education, Analytics, Consumer, Payments
```

С другой стороны, наиболее скоррелированные с описанием теги включают:

```
Next-gen Network Security, DevSecOps, eLearning, LegalTech, Music, E-Commerce,
Social, Email, ML, Media, Recruiting, Robotics, Hard Tech, Digital Health
```

Модель, безусловно, оставляет пространство для доработки, однако выявленные
с её помощью непосредственные закономерности представляют собой интересные
результаты сами по себе.

### Состояние проекта - 08.12.2023
Название компании исключено из датасета, заменена функция потерь (на бинарную
кросс-энтропию с поправкой на веса классов), добавлены метрики (accuracy,
precision, recall). В результате получена более эффективная модель. Выводы,
полученные в предыдущем случае, сохраняют актуальность: модель предсказывает
наиболее частные теги для большинства стартапов безотносительно к информации о
них. Однако в текущем состоянии модель предсказывает и собственные теги
стартапов примерно с 50% частотой.

### Состояние проекта - 30.11.2023
Получена работоспособная модель, проведён инференс на датасете. Модель обучена
не идеально, есть простор для улучшения. На данный момент модель приняла
стратегию уверенного предсказания наиболее популярных тегов для всех стартапов,
уделяя незначительное внимание содержимому описания. Это может говорить о том,
что наиболее популярные теги _(SaaS, B2B, Fintech, Developer Tools, Artificial
Intelligence, Marketplace, AI, Machine Learning, E-Commerce, Education,
Analytics)_ в значимой части случаев ставятся не будучи непосредственно
упомянутыми в описании.

### Состояние проекта - 24.11.2023
Значительно оптимизирована архитектура модели, что сделало возможным локальное
обучение. Также исправлен заведомо некорректный выбор функции потерь. Также
из чекпойнта исключены веса предобученной модели обработки текста.

Обучение в процессе, выводы об эффективности решения будут сделаны позже.

### Состояние проекта - 23.11.2023
На данный момент реализована обработка датасета и архитектура модели. Обучение
модели представляет некоторую трудность из-за проблем с аппаратным обеспечением.
Участие в обучении модели со стороны других желающих лиц приветствуется.

На данный момент результаты кратковременного обучения показывают ухудшающуюся
эффективность предсказания. Это может свидетельствовать либо о технической
проблеме в архитектуре сети, либо об отсутствии значимой обусловленности
тегов стартапа YC на его название и описание.

На следующей итерации разработки я предполагаю опробовать другую функцию потерь,
а также, как следствие, инкорпорировать нелинейное преобразование выходных
весов в саму модель (против текущего состояния, где log-softmax проводится в
рамках подсчёта кросс-энтропии).

Также хотелось бы оптимизировать размер сохраняемых контрольных точек -- на
данный момент из-за содержащихся в них весов модели DistilBert они имеют
весьма внушительный размер, не позволяющий добавить их в этот репозиторий.
