# Лабораторна робота №5

## Тема: "Деплой проекту на AWS EC2."

Виконала студентка 3 курсу

Напрям "ІПЗ" група 1.2

Копчак Ірина Сергіївна

### План:
1. Зареєструватись на AWS.

Я зареєструвалась на AWS для виконання лабораторної роботи №4, тож просто здійснюю вхід у свій акаунт

![image1](/images/1.jpg)

2. Створити інстенс ЕС2.

Створюю інстанс EC2:

![image1](/images/2.jpg)

Вибираю ОС:

![image1](/images/3.jpg)

Генерую пару ключів для нього:

![image1](/images/4.jpg)

Виконую мережеві налаштування:

![image1](/images/5.jpg)

Готовий інстенс:

![image1](/images/6.jpg)

3. Задеплоїти проект і скинути посилання у звіт для можливості перегляду.

Конекчусь до свого інстансу за допомогою відповідних команд за допомогою SSH-ключа

![image1](/images/7.jpg)

![image1](/images/8.jpg)

Оновлюю поточну базу даних з доступними для встановлення пакетами з програмним забезпеченням, після чого встановлюю вебсервер nginx

![image1](/images/9.jpg)

![image1](/images/10.jpg)

Створюю папки lab5 та html у var/www/, створюю файл index.html(для наступного деплою на aws-інстанс) та переміщую його у папку html, що я створила. Також змінюю дозволи папок.

![image1](/images/11.jpg)

![image1](/images/12.jpg)

Вміст файлу index.html:

```
<p>Iryna Kopchak IPZ1.2</p>
```

Далі я написала конфіг сервера:

![image1](/images/13.jpg)

Редагую дефолтний конфіг сервера прибираючи коментар:

```
# server_names_hash_bucket_size_64;
```

Перезапускаю сервер:

![image1](/images/14.jpg)

Заходжу на посилання свого інстансу:

![image1](/images/16.jpg)

Посилання на мій інстанс:

[3.122.224.48](http://3.122.224.48)

Висновок: на цій лабораторній роботі я навчилась створювати інстанси ЕС2 за допомогою графічного інтерфейсу AWS та деплоїти на ниї свій проект.
