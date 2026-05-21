# Morpheme-Level Levenshtein Distance for Slavic Intercomprehension

Репозиторий содержит данные и код для курсовой работы, посвящённой исследованию влияния морфемных расстояний на взаимопонятность славянских языков для носителей русского языка.

## Основная идея

Расстояние Левенштейна обычно считается для полных словоформ или с разделением на основу и флексию. В данной работе расстояние измеряется **отдельно для каждой морфемы** (префикс, корень, суффикс, окончание, постфикс), а затем полученные значения используются как предикторы в линейной и логистической регрессиях.

## Структура репозитория
- [data](https://github.com/pulciblight/morpheme_levenstein/tree/main/data) содержит csv-файлы с исходным разделением на морфемы ([morphemic_parse](https://github.com/pulciblight/morpheme_levenstein/tree/main/data/morphemic_parse)) и файлы для построения регрессий ([regression_files](https://github.com/pulciblight/morpheme_levenstein/tree/main/data/regression_files)), где вручную были дополнены данные о расстоянии Левенштейна между морфемами. Исходные данные для разбиения на морфемы можно найти в репозитории [russian_intelligibility](https://github.com/slavicintelligibility2023/russian_intelligibility).

- [notebooks](https://github.com/pulciblight/morpheme_levenstein/tree/main/notebooks) содержит три тетрадки Jupyter Notebook:
    - [levenshtein.ipynb](https://github.com/pulciblight/morpheme_levenstein/blob/main/notebooks/levenshtein.ipynb). Берет на вход файлы папки [morphemic_parse](https://github.com/pulciblight/morpheme_levenstein/tree/main/data/morphemic_parse) и считает ненормализованные расстояния Левенштейна между парами морфем, отправляя сложные случаи на ручную проверку. Разборы перципиантных синонимов извлекались вручную из сравнений с файлом [user_answers_morphs.csv](https://github.com/pulciblight/morpheme_levenstein/blob/main/data/morphemic_parse/user_answers_morphs.csv).
    - [regression_lin.ipynb](https://github.com/pulciblight/morpheme_levenstein/blob/main/notebooks/regression_lin.ipynb). Берет на вход файлы папки [regression_files](https://github.com/pulciblight/morpheme_levenstein/tree/main/data/regression_files) и строит по ним линейные регрессии с визуализациями.
    - [regression_log.ipynb](https://github.com/pulciblight/morpheme_levenstein/blob/main/notebooks/regression_log.ipynb). Берет на вход файлы папки [regression_files](https://github.com/pulciblight/morpheme_levenstein/tree/main/data/regression_files) и строит по ним логистические регрессии с визуализациями.
