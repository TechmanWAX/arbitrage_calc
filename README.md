# Арбитражный калькулятор
Just a calculator that will help you calculate the profit and Margin Call on arbitrage transactions.

Программа предназначена для отображения текущего или желаемого профита и цены ликвидации.

![изображение](https://github.com/user-attachments/assets/457ad187-e286-47f6-a913-acde167a9c8e)

Программа умеет расчитывать цену ликвидации по связкам Акция-Акция и Акция/Фьючерс.

Курс доллара берёт с сайта инвестинг онлайн. Когда поле с курсом красное, значит нет соединения с сервером
или котировки взяты из сохранённого конфига. Когда поле зелёное, значит программа соединилась с сервером
и получает котировки с него.

В программе необходимо заполнить поля просадки по акциям и фьючерсам и указать пэйаут.
Выбрать необходимую связку для которой указать количество и направление лотов, а также цены входа.
Средняя точка входа будет рассчитана автоматически.

Программа подсвечивает красным поля если количество лотов выбрано не верно.

Когда указана средняя точка выхода в поле "Выход", то профит будет расчитываться по разнице между точками входа и выхода, по первой позиции, не учитывая возможные изменения цены.

Ликвидация для акций рассчитывается по разнице в цене. А для связки Моэкс/Форекс только для позиции на Моэксе.

Все инструменты для отображения добавляются в файле 'assets.json'
Настройки всех полей программы сохраняются в файле 'gui_config.json'

Для соединения с серверами форекса и моэкса необходимо заполнить следующие данные в файле config.json:
1. для форекса необходимо создать новый торговый счёт в xpbee, standard hedging. т.к. он будет использоваться для получения рыночных данных пополнять его не нужно.
2. В программе xpbee необходимо переключиться на этот счёт:
![изображение](https://github.com/user-attachments/assets/f6f51327-d0da-4ae4-b059-0d21a104a161)
3. Затем перейти в настройки и установить пароль.
![изображение](https://github.com/user-attachments/assets/1b559ec2-3323-493f-8f51-a6d78bc18803)
5. Номер нового счёта и пароль необходимо записать в соответствующие поля в файле config.json
![изображение](https://github.com/user-attachments/assets/af9eeeb5-83f5-4680-afb0-649e708ea9d7)
6. Для получения рыночных данных с МОЭКС необходимо зарегистрироваться у брокера Алор и получить токен для доступа к API, как написано в руководстве: https://alor.dev/docs/api/quick-start/prod-env
7. Полученный токен необходимо вставить в соответствующее поле файла config.json
![изображение](https://github.com/user-attachments/assets/1e8cd766-ef3f-450f-b2f0-c93126e7543f)




Создаём в дизайнере нужную форму и преобразуем её в питон код при помощи команды:
pyuic6.exe design/main_window.ui -o design/main_window.py
Для генерации exe файла используем команду:
auto-py-to-exe.exe
