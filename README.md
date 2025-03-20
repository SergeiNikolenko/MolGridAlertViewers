
# MolGridAlertViewers

## Описание
Этот репозиторий содержит несколько Python-классов и вспомогательных скриптов для:
- Визуализации молекул из SDF-файлов
- Проверки химических структур на соответствие различным наборам алерт-фильтров (MCF, PAINS, WEHI, Dundee и др.)
- Подсветки атомов и связей с помощью RDKit при совпадении по субструктуре
- Расчёта и отображения оценок SYBA или других метрик в гриде с помощью mols2grid

## Основные модули
1. **SDFAlertGridViewer**  
   - Загружает и обрабатывает молекулы из SDF-файлов или списка SMILES
   - Проверяет структуру на соответствие набору фильтров (указываются в CSV)
   - Создаёт DataFrame c результатами и отображает их в интерактивном grидe

2. **SDFGridViewer**  
   - Показывает молекулы из SDF-файла и вычисляет SYBA-оценку
   - Рисует интерактивный грид с колоночной сортировкой и превью молекул

3. **SDFMedChemGridViewer3Filters**  
   - Загружает молекулы из SDF-файла
   - Применяет три набора фильтров (MCF, PAINS, WEHI)
   - Подсвечивает совпадающие фрагменты
   - Отображает результаты в гриде, с возможностью фильтрации по итоговому скору

## Установка зависимостей
Проект использует Python 3 и следующие библиотеки:
- [RDKit](https://www.rdkit.org/)
- [pandas](https://pandas.pydata.org/)
- [datamol](https://datamol.io/)
- [mols2grid](https://github.com/cbouy/mols2grid)
- [ipywidgets](https://ipywidgets.readthedocs.io/en/latest/)
- [joblib](https://joblib.readthedocs.io/en/latest/)
- [tqdm](https://github.com/tqdm/tqdm)

Для установки:
```bash
pip install rdkit-pypi pandas datamol mols2grid ipywidgets joblib tqdm
```

> **Примечание**: Если `rdkit-pypi` недоступен для вашей среды, см. [документацию RDKit](https://www.rdkit.org/docs/Install.html).

## Структура репозитория
```
MolGridAlertViewers/
│
├── SDFAlertGridViewer.py
├── SDFGridViewer.py
├── SDFMedChemGridViewer3Filters.py
├── data/
│   ├── alert_collection.csv      # Пример набора алерт-фильтров
│   ├── mcf.csv                   # Набор MCF-фильтров
│   ├── pains.txt                 # Набор PAINS-фильтров
│   ├── wehi_pains.csv            # Набор WEHI-фильтров
│   └── ...
└── README.md
```
