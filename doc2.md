---
description: >-
  Bu bölümdə artıq yükləmələrlə bağlı olan şeyləri bitirmiş və ilk Django
  app-imizi yazmağa hazır vəziyyətdə olduğumuzu təsəvvür edirəm.
---

# İlk Django app-imizi yazaq

Django-nun rəsmi dokumentasiyasına uyğun olaraq, Djangonu nümunə səsvermə proyekti yazaraq öyrənəcəyik. Səsvermə proyektimiz iki hissədən ibarət olacaq.

1. İnsanların səslərə baxdığı və səs verə bildiyi public sayt
2. Səslərə baxmağa, dəyişməyə və silməyə imkan verən admin saytı

Aşağıdaki komandanı yazaraq öz proyektimizi başlada bilərik:

```text
(yeniproyekt) $ django-admin startproject menimsaytim
```

{% hint style="warning" %}
Django proyektlərinə ad verərkən, `django`, `test` kimi adlardan qaçmaq lazımdır. Onlar konflikt yaradırlar.
{% endhint %}

Diqqət etsəniz görərsiniz ki, virtual mühitdə istifadə etdiyimiz python versiyası 3.x-dür. Ona görə də, virtual mühitdə olarkən python3 yazmağımıza ehtiyac yoxdur.

Aşağıdakı komandanı yazaraq, proyektimizi run edə bilərik.

```text
(yeniproyekt) $ cd menimsaytim/
(yeniproyekt) $ python manage.py runserver
```

Əgər virtual serverin browserindən [http://127.0.0.1:8000](http://127.0.0.1:8000) adresinə girsəniz,  `The install worked successfully! Congratulations!` yazısı görəcəksiniz. Əgər gördünüzsə, sizi təbrik edirəm! 🥳 







