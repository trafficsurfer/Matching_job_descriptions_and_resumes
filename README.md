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
- pipeline.ipynb
### Эксперименты

### Схема работа сервиса
![image](https://github.com/trafficsurfer/Matching_job_descriptions_and_resumes/assets/92330362/4df893e7-8e39-4134-b027-4a0bc6bb351c)
### Пример работы модели
#### Резюме по вакансии
![image](https://github.com/trafficsurfer/Matching_job_descriptions_and_resumes/assets/92330362/f0fae8bc-f232-464a-9514-33ea57f4651e)
#### Вакансии по резюме
![image](https://github.com/trafficsurfer/Matching_job_descriptions_and_resumes/assets/92330362/7537cfff-b281-486e-b680-6bc2dffa7809)



