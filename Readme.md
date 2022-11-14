# Лабораторна робота №6

## Тема: "Використання GitHub Actions."

Виконала студентка 3 курсу

Напрям "ІПЗ" група 1.2

Копчак Ірина Сергіївна

### План:
1.  Ознайомитись із поняттями CI/CD та GitHub Actions.

Безперервна інтеграція (Continuous Integration, CI) і безперервне постачання (Continuous Delivery, CD) є набором принципів і практик, які дозволяють розробникам частіше і надійніше розгортати зміни програмного забезпечення.

Безперервна інтеграція(Continuous Integration, CI) — це методологія розробки та набір практик, за яких код вносяться невеликі зміни з частими комитами. І оскільки більшість сучасних додатків розробляються з використанням різних платформ та інструментів, то виникає потреба в механізмі інтеграції та тестуванні змін, що вносяться.

З технічної точки зору, мета CI — забезпечити послідовний та автоматизований спосіб складання, пакування та тестування додатків. При налагодженому процесі безперервної інтеграції розробники з більшою ймовірністю робитимуть часті комміти, що, у свою чергу, сприятиме покращенню комунікації та підвищенню якості програмного забезпечення.

Інструменти CI/CD допомагають налаштовувати специфічні параметри оточення, які конфігуруються під час розгортання. А також CI/CD-автоматизація виконує необхідні запити до веб-серверів, баз даних та інших сервісів, які можуть потребувати перезапуску або виконання якихось додаткових дій під час розгортання програми.

Безперервна інтеграція та безперервне постачання потребують безперервного тестування, оскільки кінцева мета — розробка якісних додатків. Безперервне тестування часто реалізується у вигляді набору різних автоматизованих тестів (регресійних, продуктивності та інших), які виконуються у CI/CD-конвеєрі.

Зріла практика CI/CD дозволяє реалізувати безперервне розгортання: при успішному проходженні коду через CI/CD-конвеєр, збірки автоматично розгортаються у продакшн-оточенні. Команди, які практикують безперервне постачання, можуть дозволити собі щоденне або навіть щогодинне розгортання. Хоча тут варто відзначити, що безперервне постачання підходить не для всіх бізнес-додатків.

GitHub Actions — це платформа безперервної інтеграції та безперервної доставки (CI/CD), яка дозволяє вам автоматизувати збірку, тестування та розгортання. Ви можете створювати робочі процеси, які створюють і тестують кожен запит на отримання до вашого сховища, або розгортати об’єднані запити на отримання в робочому середовищі.

GitHub Actions виходить за рамки просто DevOps і дозволяє запускати робочі процеси, коли у вашому сховищі відбуваються інші події. Наприклад, ви можете запустити робочий процес, щоб автоматично додавати відповідні мітки щоразу, коли хтось створює нову проблему у вашому сховищі.

2. Задеплоїти проект на EC2 або VPS(за наявності) за допомогою GitHub Actions. 

Спочатку я створила інстанс EC2 на AWS з такими ж налаштуванням як у лабораторній №5. Потім я створила файл index.html та закомітила його у нову гілку lab_work_six у репозиторій Labworks-OS на GitHub.

Далі у репозиторії зайшла у Settings -> Actions -> Runners

![image1](/images/1.jpg)

Створюю self-host runner для представлення Лінукс(оскільки я при створенні інстансу на AWS обрала ОС Лінукс):

![image1](/images/2.jpg)

Вхід у інстанс за допомогою згенерованого при створенні інстансу SSH-ключа:

![image1](/images/3.jpg)

Виконую наступні команди з Settings -> Actions -> Runners свого репозиторію у командному рядку:

![image1](/images/4.jpg)

Виконую налаштування ранеру(залишаю все за замовчуванням) та активую його:

![image1](/images/5.jpg)

![image1](/images/6.jpg)

Оновлюю сторінку налаштувань репозиторію і тепер бачимо, що ранер дійсно активізувався:

![image1](/images/7.jpg)

Встановлюю вебсервер nginx:

![image1](/images/8.jpg)

3. Ознайомитись із github pipelines та використати їх для реалізації CI/CD.

У своєму репозиторії заходжу на вкладку Actions та редгую pipeline за замовчуванням:

![image1](/images/9.jpg)

![image1](/images/10.jpg)

![image1](/images/11.jpg)

Білдинг проекту:

![image1](/images/12.jpg)

Пишу конфіг сервера:

![image1](/images/14.jpg)

Заходжу за посиланням свого інстансу:

![image1](/images/15.jpg)

Тепер при кожному коміті проект буде ребілдитись.

Висновок: на цій лабораторній роботі я ознайомилась із поняттями CI/CD та GitHub Actions, навчилась деплоїти проект на EC2 за допомогою GitHub Actions,
ознайомилась із github pipelines та використала їх для реалізації CI/CD.