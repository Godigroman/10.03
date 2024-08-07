# Домашнее задание к занятию "`SQL. Часть 1`" - `Клименко Олег`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

```
SELECT DISTINCT district FROM address WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```

![](https://cdn.discordapp.com/attachments/1258765840971464767/1263406348591304826/1.png?ex=669a1e5a&is=6698ccda&hm=3cbce536feac2cc14f7fb8f2574c8038352e72cb56065af3cb4d1cc3b00eb8d8&)

---

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

```
SELECT amount, payment_date FROM payment WHERE amount > 10 AND payment_date BETWEEN '2005-06-15 00:00:00' AND '2005-06-18 23:59:59';
```

![](https://cdn.discordapp.com/attachments/1258765840971464767/1263406578074386453/2.png?ex=669a1e91&is=6698cd11&hm=d9a5f9d5237d895c7f8f0ee05e97e9924b61649504a28f1e58bae36d783011d9&)

---

### Задание 3

Получите последние пять аренд фильмов.

```
SELECT rental_id, rental_date, last_update  FROM rental ORDER BY rental_date DESC, rental_id DESC LIMIT 5;
```

![](https://cdn.discordapp.com/attachments/1258765840971464767/1263406831032729664/3.png?ex=669a1ecd&is=6698cd4d&hm=3c3926b15ec9d3be6ac0efe8e510125ba3c4af50dfb6efd4065b47d1cbc44987&)

---

Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

```
SELECT LOWER(first_name), LOWER(last_name), REPLACE(LOWER(first_name), 'll', 'pp')as ll_TO_pp FROM customer WHERE first_name LIKE 'Kelly' OR  first_name  LIKE 'Willie';
```

![](https://cdn.discordapp.com/attachments/1258765840971464767/1263407212651614208/4.png?ex=669a1f28&is=6698cda8&hm=542376c4c230a41ed7c16cef4b23900f00df927ecf7b73122b912747c2516ee1&)

---
---
