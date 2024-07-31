# Credit-risk-banks
Построить модель оценки вероятности отзыва банковской лицензии по данным отчётности банка.
Данные
Мы будем использовать данные по отзыву банковских лицензий и банковской отчётности с сайта
ЦБ РФ. Информация по кредитным рейтингам бесплатно доступна на сайте. Вы можете либо
распарсить эти сайты, либо найти эту же информацию в более удобном для машинной обработки
виде в разнообразных базах данных, доступных по подписке ВШЭ. При необходимости можно
использовать дополнительную информацию.
Задание
1. Сформируйте целевую переменную. Обратите внимание на то, что существуют разные
причины отзыва банковской лицензии (см. лекцию 4). Обратите внимание на формулировку
как целевого события, так и горизонта.
2. Сформируйте необходимое для обучения число подвыборок. Обоснуйте как способ
формирования общей выборки (как именно формируются строки в таблице, чтобы
избежать утечки данных), так и способ разбиения на подвыборки. Остерегайтесь
автоматического разбиения — ввиду сравнительно малого объёма выборки возможны
статистические артефакты.
3. Постройте модель предсказания вероятности отзыва лицензии. Интерпретируемость здесь
не обязательна, но при выборе структуры моделей учтите ограниченность данных. Для
построения модели:
a. проведите предварительный анализ данных;
b. отберите переменные для анализа, руководствуясь предварительным анализом и
здравым смыслом (проводите однофакторный и многофакторный анализ);
c. постройте модель и оцените её качество;
d. по возможности, интерпретируйте оценённую зависимость в терминах влияния
отдельных признаков и их комбинаций, если они вошли в модель, на вероятность
дефолта.
4. Постройте аналогичную модель на основе исключительно кредитных рейтингов,
присваиваемых банкам кредитными рейтинговыми агентствами. Для целей задания
достаточно использовать рейтинги одного кредитного рейтингового агентства, однако для
улучшения результатов вы можете использовать рейтинги нескольких агентств — не
забудьте описать, как именно вы это сделали. Кратко опишите результаты.
5. Проведите валидацию обеих построенных моделей, сравнивая их друг с другом. Вы можете
выбирать тесты для валидации самостоятельно, руководствуясь материалами курса,
научными и методическими работами, нормативными документами ЦБ и других
национальных регуляторов, документами Базельского комитета и пр. Необходимо
раскрыть, по меньшейDмере, следующие аспекты (на каждый аспект можно делать более
одного теста, если это нужно для полноты картины).
a. Некоторые из тестов подразумевают дискретизацию предсказаний (внутренние
рейтинги, основанные на модели). Проведите эту дискретизацию один раз и в
дальнейшем используйте одно и то же разбиение непрерывного скорингового
балла на внутренние рейтинги во всех тестах.
b. Разделяющая способность модели. Продемонстрируйте, что модель хорошо
отделяет банки, у которых отозвали лицензию, от сохранивших её.
c. Переобучение. Нет ли признаков переобучения модели? 
d. Простота модели. Нельзя ли упростить модель, не сильно потеряв при этом в
качестве? Действительно ли нужны все факторы и все взаимосвязи?
e. Устойчивость модели в динамике. Продемонстрируйте, что модель стабильно
ранжирует наблюдения на всех временных срезах и отсутствуют периоды, в которых
разделяющая способность модели недостаточна.
f. Если в модели использовалась дискретизация переменных, оцените экономический
смысл разбиения переменных на именно такие категории. Нет ли необъяснимых
немонотонностей и/или неустойчивостей?
g. Корректность оценки вероятности отзыва. Проверьте, согласуются ли
предсказания вероятности отзыва и реально наблюдаемая частота отзывов. Если
нет, откалибруйте модель и продемонстрируйте, что она выполняет свою функцию.
6. Пусть на сегодняшний момент у нас есть экспозиция к банкам «Альфа-Банк», «Авангард»,
«Росбанк», «Экспобанк» и «Локо-Банк» — по 200 млн. руб. к каждому. Мы не ожидаем
изменения этой суммы. Пусть LGD = 40%. Используя обе свои модели, оцените:
a. Ожидаемые потери (математическое ожидание) и неожидаемые потери (VaR на
уровне 99.9%) на горизонте 1 год. Оцените экономический капитал как разность
этих двух величин.
b. Проведите аналогичный расчёт для горизонта 5 лет. Учтите, что на горизонте 5 лет
влияние изменения макроэкономических показателей и/или бизнес-циклов может
быть ощутимым.
c. Ожидаемые потери (математическое ожидание) и неожидаемые потери (VaR на
уровне 99.9%) на горизонте 1 год с учётом корреляции между отзывами
банковских лицензий.
7. Оценка по какой из моделей (на основе кредитных рейтингов или на основе отчётности)
вам видится более адекватной? Аргументируйте выбор в первую очередь результатами
валидации обеих моделей с использованием дополнительной информации по желанию.
Отчётные материалы
1. Отдельно ответы на вопрос 6 — по каждой из двух построенных моделей. Эта информация
будет использоваться нами в агрегированном виде. Мы поделимся статистикой после
защит. Всего нужно отдельно сдать:
a. ожидаемые потери и размер капитала для модели по отчётности для горизонта 1
год (точечная оценка и 99% доверительный интервал);
i. то же самое для модели по кредитным рейтингам;
b. ожидаемые потери и размер капитала для модели по отчётности для горизонта 5
лет (точечная оценка и 99% доверительный интервал);
i. то же самое для модели по кредитным рейтингам;
c. ожидаемые потери и размер капитала для модели по отчётности для горизонта 1
год с учётом корреляций между отзывами лицензий (точечная оценка и 99%
доверительный интервал);
i. то же самое для модели по кредитным рейтингам. 
