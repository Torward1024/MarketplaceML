# 🚀 Предсказание покупательской активности пользователей интернет-магазина
![Python](https://img.shields.io/badge/Python-3.12%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.2%2B-orange)
![NumPy](https://img.shields.io/badge/NumPy-2.2%2B-green)
![Phik](https://img.shields.io/badge/Phik-0.12%2B-purple)
![Joblib](https://img.shields.io/badge/Joblib-1.4%2B-purple)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10%2B-red)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13%2B-lightgrey)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.6%2B-yellow)
![Imbalanced-learn](https://img.shields.io/badge/Imbalanced--learn-0.14%2B-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-3.0%2B-green)
![CatBoost](https://img.shields.io/badge/CatBoost-1.2%2B-purple)
![SHAP](https://img.shields.io/badge/SHAP-0.48%2B-blue)

## 🎯 Цель проекта
Разработать модель машинного обучения для прогнозирования вероятности совершения покупки пользователем в течение 90 дней на основе исторических данных о покупках и взаимодействии с рекламными рассылками.

## 📌 Задачи
- Изучить данные;
- Разработать полезные признаки;
- Создать модель для классификации пользователей;
- Улучшить модель, провести анализ важности признаков, максимизировать метрика ```roc_auc```;
- Выполнить тестирование модели.

## 🔍 Описание данных

1. **apparel-purchases** — история покупок:
   - `client_id` — идентификатор пользователя
   - `quantity` — количество товаров
   - `price` — цена товара
   - `category_ids` — категории товара
   - `date` — дата покупки
   - `message_id` — идентификатор сообщения рассылки

2. **apparel-messages** — история рекламных рассылок:
   - `bulk_campaign_id` — идентификатор кампании
   - `client_id` — идентификатор пользователя
   - `message_id` — идентификатор сообщения
   - `event` — тип действия (send, click, open, purchase и др.)
   - `channel` — канал рассылки (email, mobile_push)
   - `date` — дата события

3. **apparel-target_binary** — целевая переменная:
   - `client_id` — идентификатор пользователя
   - `target` — совершит покупку в течение 90 дней (1/0)

### Ключевые разработанные признаки
- Поведенческие показатели пользователей: `recency_days`, `lifespan_days`, `purchase_days`;
- Маркетинговые показатели: `ctr`, `conversion_rate`, `open_rate`, `unsubscribe_rate`;
- Временные паттерны: активность за 30/60/90 дней;
- Популярные категории товаров;
- Эффективность каналов mobile_push и email.

## 🛠 Технологический стек
- **Анализ данных**: Pandas, NumPy
- **Визуализация**: Matplotlib, Seaborn
- **Машинное обучение**: Scikit-learn, XGBoost
- **Обработка времени**: datetime, timedelta
- **Разработка**: Jupyter Notebook, Git

## 📊 Ключевые результаты

### Топ-5 наиболее важных признаков:
1. **lifespan_days** -- продолжительность взаимодействия с платформой
2. **recency_days** -- дней с последней покупки
3. **conversion_rate** -- конверсия из клика в покупку
4. **event_click_last_60d** -- клики за 60 дней
5. **purchase_days** -- уникальные дни с покупками

### Ключевые факторы для последующих покупок:
- Длительность отношений с магазином -- приоритетный показатель
- Недавние взаимодействия с рассылками значительно повышают вероятность покупки
- Конверсия из клика в покупку важнее общего количества кликов
- Mobile-push уведомления показывают лучшую результативность

### Рекомендации для бизнеса:
- Сфокусироваться на удержании существующих клиентов с длительной историей;
- Оптимизизровать mobile-push канал рассылки рекламных предложений как наиболее эффективный;
- Персонализировать рассылки на основе предпочтений пользователей;
- Работа с клиентами, показывающими снижение активности;

## 📂 Структура проекта
MarketplaceML/\
├── data/                       # Папка с исходными данными (в репозитории не представлена)\
├── notebook.ipynb              # Тетрадка с проектом\
├── requirements.txt            # Зависимости\
└── README.md                   # Этот файл

### Метрики модели:
- **Accuracy**: 0.7574
- **Precision**: 0.0481
- **Recall**: 0.6167
- **F1-score**: 0.0892
- **F2-score**: 0.1832
- **ROC-AUC**: 0.7704

## 📞 Контакты
- Автор: Алексей Рудницкий
- Email: almax1024@gmail.com
- Telegram: @torward1024
