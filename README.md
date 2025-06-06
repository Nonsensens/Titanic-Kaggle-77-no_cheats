# 🎯 Titanic Survival Prediction (Kaggle)

> Прогнозирование выживания пассажиров Титаника с использованием современных моделей машинного обучения и глубокого обучения. Проект включает стекинг, AutoML и кастомную нейросеть на PyTorch. Уровень 0.77

---

## 📦 Описание

Проект реализует полноценный ML-пайплайн для задачи классификации (`binary classification`) на датасете [Kaggle: Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic).

Мы исследуем и сравниваем классические алгоритмы, ансамбли, стекинг моделей, кастомную нейросеть на PyTorch и автоматические инструменты типа AutoGluon.

---

## 🛠️ Использованные технологии

- `pandas`, `seaborn`, `matplotlib` — для EDA и визуализации
- `scikit-learn` — RandomForest, LogisticRegression, Stacking
- `XGBoost` — градиентный бустинг
- `PyTorch` — глубокая нейронная сеть
- `AutoGluon` — AutoML стекинг и блендинг
- `Google Colab` — запуск и обучение

---

## 📊 Результаты

| Модель                  | Accuracy | F1-score | ROC AUC |
|------------------------|----------|----------|---------|
| 🏆 AutoGluon Ensemble   | 0.916    | 0.889    | 0.906   |
| 🔁 Manual Stacking      | 0.827    | 0.770    | 0.812   |
| 🎯 XGBoost              | 0.827    | 0.770    | 0.812   |
| 🌲 Random Forest        | 0.793    | 0.752    | 0.794   |
| 📉 Logistic Regression  | 0.765    | 0.716    | 0.764   |
| 🧠 PyTorch Neural Net   | 0.782    | 0.707    | 0.762   |

> 🔬 *AutoGluon показал лучший результат по всем ключевым метрикам без ручной настройки.*

---

## 📈 EDA и фиче-инжиниринг

- Обработка пропущенных значений (`Age`, `Cabin`, `Embarked`)
- Создание новых признаков: `Title`, `FamilySize`, `IsAlone`, `FareBin`, `AgeBin`
- Label encoding и one-hot
- Масштабирование и нормализация (для нейросети)

---

## 🧠 Архитектура нейросети (PyTorch)

- `Input → Linear(256) + BatchNorm + SELU`
- `→ Linear(128) + BatchNorm + SELU`
- `→ Linear(64) + BatchNorm + SELU`
- `→ Output(2 classes)`
- Оптимизатор: `Adam`
- Функция потерь: `CrossEntropyLoss`

---

## 🚀 Как запустить
```bash
pip install -r requirements.txt
Запустите ноутбук: titanic_kaggle.ipynb
```
---

## 📌 Вывод
📈 Модель AutoGluon продемонстрировала SOTA-результат (F1 = 0.89), обойдя вручную собранные ансамбли и глубокую нейросеть.
Проект иллюстрирует, как можно комбинировать разные подходы — от классики до AutoML — для достижения максимально точных решений на реальных задачах.
