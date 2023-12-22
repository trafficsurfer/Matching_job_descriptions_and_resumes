# Матчинг описания вакансий и резюме
### Цель проекта
Разработка и реализация программного решения для сопоставления текстовых описаний вакансии и резюме.
### Описание проекта 
Разработка сервиса для платформы по поиску работы и сотрудников, позволяющего измерить релевантность резюме соискателя и вакансии. Задача приложения - выдавать численную оценку, насколько конкретный соискатель отвечает требованиям вакансии.
### Потенциальные варианты использования сервиса на платформе
- улучшение поиска вакансий соискателями
- рекомендация вакансий
- фильтрация нерелевантных кандидатов hr-специалистами <br />
### Данные
[Датасет резюме HeadHunter](https://drive.google.com/file/d/1ikA_Ht45fXD2w5dWZ9sGTSRl-UNeCVub/view) <br />
[Датасет вакансий HeadHunter](https://www.kaggle.com/datasets/etietopabraham/jobs-raw-data/data)
### Описание файлов репозитория
- EDA_and_experiments.ipynb - изучение данных, очистка, эксперименты с эмбеддингами (multilingual-e5-large, FastText)
- encoders_experiment.ipynb - эксперименты с выбором модели для получения эмбеддингов
- pipeline.ipynb - итоговая очистка данных, получение и сохранение эмбеддингов multilingual-e5-large, загрузка эмбеддингов в Qdrant, семантический поиск с использованием Qdrant.
### Эксперименты
| Описание | Результат |
|-------|-------|
| Эмбеддинги из различных энкодеров: multilingual-e5-large, rubert-tiny2, MiniLM-L12-v2, DeepPavlov rubert-base-cased-sentence | multilingual-e5-large показала наилучшие результаты по качеству получаемых эмбеддингов - в топ релевантных вакансий семантического поиска попадают результаты с идентичной должностью. Кроме того, есть совпадения по региону и преимущественная близость мэтчей в опыте работы |
| Классификатор для результатов семантического поиска | Pre-trained модели для реранжирования результатов не показали ощутимого прироста качества |
| HRBert-mini| Семантический поиск на эмбеддингах из модели “as is” дает в основном мало релевантные результаты |
| Эмбеддинги FastText с очисткой данных | FastText хуже улавливает семантическую близость между вакансиями и резюме, где содержание не совпадает в точности, но схоже по смыслу |
| Эмбеддинги multilingual-e5-large признаков по отдельности. Например, (эмбединги описания вакансий/резюме + эмбединги остальных признаков) | Результаты отличается незначительно от исходного варианта |
### Схема работа сервиса
![image](https://github.com/trafficsurfer/Matching_job_descriptions_and_resumes/assets/92330362/4df893e7-8e39-4134-b027-4a0bc6bb351c)
### Пример работы модели
#### Резюме по вакансии
![image](https://github.com/trafficsurfer/Matching_job_descriptions_and_resumes/assets/92330362/b4188060-99e9-4ac4-b536-36a53ff8fd57)
#### Вакансии по резюме
![image](https://github.com/trafficsurfer/Matching_job_descriptions_and_resumes/assets/92330362/7537cfff-b281-486e-b680-6bc2dffa7809)



