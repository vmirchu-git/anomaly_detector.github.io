# Anomaly Detector for Chatbot Intent Metrics

---

## 🇬🇧 English version
### Context
Before the project, chatbot quality was manually assessed using intent accuracy, user CSAT scores, and operational metrics. Data aggregation was irregular and analysis took up to 3–4 hours per cycle.  

**Problems:**  
- No automatic anomaly detection in metrics.  
- Missed sharp drops in accuracy and increases in fallback triggers.  
- Hidden degradations could remain unnoticed for up to a week.  

**Why critical:**  
Declining intent accuracy directly impacted user satisfaction (-15–20% in some cases) and increased operator workload.

### Goal
**Primary:**  
Develop an ML tool that automatically detects anomalous changes in chatbot metrics and signals potential intent issues.  

**Secondary:**  
- Reduce analytics cycle time.  
- Ensure scalability across different projects and metrics.  
- Consider specific intents (e.g., HR or junior-specific exceptions).  

**Success criteria:**  
- >90% of anomalies detected by the system are confirmed manually.  
- Time to alert: <1 hour from anomaly occurrence.

### Approach

**Action Plan:**  
1. Build metrics for all product intents (accuracy, automation rate, weight).  
2. Compute rolling-window metrics.  
3. Calculate rolling-window variance.  
4. Trigger alerts when metrics cross 2–3 sigma thresholds.  

**Methods and Models:**  
- Isolation Forest for multivariate anomaly detection.  
- IQR-based outlier detection for univariate metrics.  
- Rolling-window statistical analysis for trend monitoring.  

**Metrics:**  
- Precision / Recall for anomaly detection.  
- F1-score as a balanced indicator.  
- Mean Time To Detect (MTTD) — average time to detect anomalies.

### Results

**Quantitative:**  
- Detection of 95% of degradation cases confirmed manually.  
- Reduction of analysis time from 3–4 hours to <30 minutes per cycle.  

**Qualitative:**  
- Early identification of degrading intents.  
- Flexible adjustment for different projects.  
- Detection of hidden correlations between metrics.  

**Side effects:**  
- Initial system generated more false positives for rare intents — resolved by calibration.

### Business Impact

**Effect:**  
- Reduced cases of critical quality drops.  
- Saved analysts’ time by automating routine monitoring.  

**Resource savings:**  
- Reduced manual intent checks.  

**Quality improvement:**  
- Overall increase in chatbot accuracy and consistency.  
- Built visualizations for trends and anomaly monitoring across intents.

---

## 🇷🇺 Русский вариант 
**Технологии:** Python • pandas • numpy • matplotlib • seaborn • statsmodels 

### Контекст
До проекта качество работы чат-бота оценивалось вручную по точности интентов, CSAT и служебным метрикам. Данные агрегировались нерегулярно, анализ занимал до 3–4 часов на цикл.  

**Проблемы:**  
- Отсутствие автоматической сигнализации об аномалиях.  
- Пропуск резких падений accuracy и роста fallback-запусков.  
- Скрытые деградации могли оставаться незамеченными до недели.  

**Почему критично:**  
Снижение точности интентов снижало удовлетворённость пользователей (-15–20% в отдельных случаях) и увеличивало нагрузку на операторов.

### Цель проекта

**Основная:**  
Разработать инструмент, автоматически выявляющий аномальные изменения метрик чат-бота и сигнализирующий о проблемах в интентах.  

**Второстепенные цели:**  
- Сократить время аналитического цикла.  
- Обеспечить масштабируемость на разные проекты и метрики.  
- Учитывать специфику отдельных каналов (HR и junior).  

**Критерии успеха:**  
- >90% аномалий, найденных системой, подтверждаются вручную.  
- Время реакции на проблему <1 часа.

### Подход и решение

**План действий:**  
1. Построение метрик для всех интентов (точность, автоматизация, вес).  
2. Вычисление скользящих метрик.  
3. Расчёт дисперсии скользящим окном.  
4. Алерт при пробитии метрики 2–3 сигм вниз.
5. Построить визуализации для мониторинга трендов и аномалий по интентам.  

### Результаты
- Раннее обнаружение значимых деградаций.  
- Сокращение времени анализа с 3–4 часов до <30 минут на цикл.  
- Гибкая настройка под разные проекты.  
- Выявление скрытых взаимосвязей метрик.  
- Снижение случаев критических падений качества.  
- Автоматизация рутинного мониторинга.  
- Повышение общей точности и стабильности чат-бота.  
