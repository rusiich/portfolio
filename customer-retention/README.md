# Прогнозирование снижения покупательской активности

Этот проект посвящён задаче **классификации**: построению модели для **прогнозирования вероятности снижения покупательской активности клиентов** интернет-магазина "В один клик". Цель — предложить персонализированные предложения с целью удержания клиентов.

## 🔧 Используемый стек

- `Python 3.10+`
- 📊 **Pandas** — для анализа и предобработки данных  
- 📈 **Matplotlib**, **Seaborn** — для визуализации  
- 🧪 **Scikit-learn** — для обучения моделей и оценки качества  
- ⚙️ **Pipeline** — для настройки моделей и автоматизации пайплайна  
- 💾 **SHAP** — для оценки важности признаков  

## 📁 Структура проекта

- `customer_activity_prediction.ipynb` — основной ноутбук с анализом данных, обучением моделей и визуализациями  
- `README.md` — описание проекта

## ⚙️ Основные этапы

1. **Загрузка данных**:  
   - `market_file.csv`, `market_money.csv`, `market_time.csv`, `money.csv` — изучение данных о поведении клиентов, выручке, времени на сайте и прибыли от покупок.
  
2. **Предобработка данных**:  
   - Проверка данных на пропуски, дубликаты, коррекция типов данных.
  
3. **Исследовательский анализ данных**:  
   - Анализ покупательской активности за последние три месяца. Статистический анализ, выявление выбросов.
  
4. **Корреляционный анализ**:  
   - Оценка взаимосвязи признаков и устранение мультиколлинеарности.
  
5. **Создание моделей с пайплайнами**:  
   - Обработка категориальных и количественных признаков.
   - Обучение моделей:  
     - KNeighborsClassifier  
     - DecisionTreeClassifier  
     - LogisticRegression  
     - SVC

6. **Оценка качества моделей**:  
   - Сравнение моделей с использованием метрики ROC-AUC.
   - Выбор наилучшей модели и её настройка.

7. **Анализ важности признаков**:  
   - Оценка значимости признаков с использованием метода SHAP.

8. **Сегментация клиентов**:  
   - Разделение клиентов на сегменты по вероятности снижения активности и прибыльности.

## 📊 Результаты

- **Наилучшая модель**: LogisticRegression (C=1, penalty='l1', solver='liblinear')
- **Метрика**: ROC-AUC ~0.91 на тестовой выборке
- **Вывод**: Модель показала хорошее качество предсказаний, и выделены ключевые признаки, влияющие на снижение покупательской активности.

## 🧠 Выводы

### 1. Исследовательский анализ данных:
- Покупатели предпочитают товары для детей.
- Большинство клиентов разрешили получение предложений по купонам.
- Признак "неоплаченные продукты" имеет распределение Пуассона.
- Наблюдаются выбросы по признакам "Выручка" и "Акционные покупки", которые оставлены в данных для анализа.

### 2. Модели:
- Для сравнения выбрана метрика **ROC-AUC**.
- Лучшая модель — **LogisticRegression** с метрикой 0,91 на тестовой выборке.

### 3. Анализ важности признаков:
- Наиболее значимые признаки: "Страниц за визит", "Средний просмотр категорий за визит", "Время на сайте", "Неоплаченные продукты", "Акционные покупки".
- Наименее значимыми оказались "Выручка с покупателя" и "Популярные категории".

### 4. Сегментация клиентов:
- Выделены сегменты с высоким риском снижения покупательской активности, включая покупателей, склонных к акционным покупкам и имеющих неоплаченные товары в корзине.
- Рекомендации для удержания таких клиентов: персонализированные предложения, скидки на неоплаченные товары, улучшение процесса оформления заказа.

## 📝 Рекомендации

- **Для удержания клиентов**:  
  - Регулярные напоминания, вовлечение на сайте через промоакции и скидки.
  - Персонализация контента для каждого клиента.
  - Оптимизация навигации и улучшение функционала корзины.

- **Для клиентов с риском снижения активности**:  
  - Предложение скидок на товары, которые они оставили в корзине.
  - Индивидуализированные предложения для акционных покупателей.
  - Программы лояльности и накопительные бонусы.

## 📜 Заключение

Проект по анализу покупательской активности интернет-магазина продемонстрировал высокую эффективность применения моделей машинного обучения для прогнозирования вероятности снижения активности. Были предложены мероприятия для удержания клиентов, что позволит улучшить вовлечённость и прибыльность магазина.

