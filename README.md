# Локализация масконов Луны
Работа посвящена локализации масконов Луны в её гравитационном поле (аномалии силы тяжести Луны в редукции Буге с плотностью промежуточного слоя 2,55 г/см3 GRGM1200A). Рассмотрен подход на основе применения сверточных нейронных сетей архитектуры U-Net. В качестве базовых алгоритмов локализации эффектов масконов рассмотрены методы обработки изображений: адаптивное пороговое разделение, операторы Собеля и Лапласа, метод Кэнни. При этом ввиду отсутствия единой базы данных с интерпретированными аномалиями силы тяжести создана синтетическая обучающей выборка. Эффект маскона описан эффектом точечного источника, а для приближения модели поля к реальному добавлена случайная помеха. Оценка точности методов выполнена по метрике IoU (Intersection over Union) на основе сравнения с данными размеченными вручную. Наилучшие результаты показала нейронная сеть U-Net с предобученным энкодером Efficientnet-b2.

# Структура

***Папка data:***

dGb255_Merc_dx5km.grd - грид аномалий силы тяжести Луны в редукции Буге Луны. Шаг дескретизации 5 км. Проекция Меркатора  
dGb255_Merc_dx20km.grd  - грид аномалий силы тяжести Луны в редукции Буге Луны. Шаг дескретизации 20 км. Проекция Меркатора  
Manual_mask_dx5km.grd - грид с максой масконов по результатам ручной разметки. Шаг дескретизации 5 км. Проекция Меркатора  
Manual_mask_dx20km.grd  - грид с максой масконов по результатам ручной разметки. Шаг дескретизации 5 км. Проекция Меркатора  

***Папка notebooks:***

**Запускать блокноты следует по порядку**
0_OpenCV_segm_models.ipynb - блокнот Jupyter с локалдизацией масконов методами: адаптивное пороговое разделение, операторы Собеля и Лапласа, метод Кэнни  
1_Training_array_creation.ipynb - блокнот Jupyter для созлдания обучающей выборки  
2_NN_SMP_model.ipynb  - блокнот Jupyter для обучения нейронной сети  
3_CNN_apply.ipynb - блокнот Jupyter для применения обученной нейронной сети  

***Папка weights:***

25_05_30_model_600_Unet_effb2_ВСЕ1_192.pth - пример обученной модели архитектуры U-Net с энкодером Efficientnet-b2.

# Благодарности
Работа выполнена при большой поддержке Некоммерческого фонда содействия развитию науки и образования «ИНТЕЛЛЕКТ» и моего наставника Никиты Белякова
