---
description: >-
  Django-nu necə hazırlamalı sualını 100 nəfərə versəniz 101 fərqli cavab
  alacaqsınız. Mənim cavabım:
---

# Mühitin hazırlanması

## Quraşdırılma

İstifadəçilər Djangonu quraşdırarkən fərqli xətalarla qarşılaşa bilirlər. Bunların qarşısını almaq üçün bu dərsdə hamının mühitinin eyni olmasına çalışacağam.  
Öz mühitimizi Ubuntu üzərində quracayıq. Virtual serverə quracağımız ubuntu.iso faylını aşağıdaki linkdən yükləyə bilərsiniz.

Mən sistemi qurarkən əlavə olaraq `alicenab` adında istifadəçi də açdım. Bundan sonraki bütün komandaları həmin istifadəçidən edəcəyəm.

```bash
wget http://releases.ubuntu.com/18.04.3/ubuntu-18.04.3-live-server-amd64.iso
```

{% hint style="warning" %}
Django istifadəsi üçün Python3 məsləhət görülür çünki Python2.7-yə olan dəstək 2020-ci ildə bitəcək. Nəzərə alsaq ki, Ubuntu 18.04 özü ilə birlikdə python3 də yükləyir. Bu baxımdan bizim üçün problem olmayacaq.
{% endhint %}

Virtual Serverdə Ubuntunu əlavə paketlər olmadan \(installing prosesində sondaki paketləri seçmədən\) pure şəkildə quraşdırdım. Virtual maşına yeniləmirəm ki, dərsi izləyən hamı eyni mühitdə işləmiş olsun. Virtual maşında snapshot aldım ki, hər hansı problem ilə qarşılaşdığımda əvvəlki vəziyyətə qayıda bilim.   
  
Gələcəkdə browserdən istifadə edəcəyimizi nəzərə alaraq, ubuntu-dekstop-u quraşdırmalıyıq.

```bash
$ sudo apt install ubuntu-desktop
```

Serverə yüklənmiş Python iki cür görsənmək ehtimalı var, python və python3. Sadə dildə desək, python 2.x versiyaları üçün, python3 isə python 3.x versiyaları üçün nəzərdə tutulub. Sistemə yüklənib yüklənmədiyini aşağıdakı qaydada yoxlamalıyıq:

```bash
$ python3 --version
Python 3.6.8
$ python --version
Command 'python' not found, but can be installed with:
---bla bla---
```

Rəsmi dokumentasiya tərəfindən Django üçün məsləhət görülən quraşdırılma metodu `pip` vasitəsiylədir. Python3-ə aid olan pip versiyası pip3-dür. Serverə pip3 quraşdırmaq üçün:

```bash
$ sudo apt install python3-pip
```

{% hint style="warning" %}
Virtual environmentlər haqqında qeyd:

Django-dan istifadə edərkən hər hansı proyekt üzərində işlədiyinizdə, həmin proyektinizin işləməsi üçün lazım olan python3 paketlərini yükləməli olacaqsınız. Təsəvvür edin ki, onlarla proyektiniz var və heç biri üçün virtual environment işlətməmisiniz. Bu halda lazımi paketləri sistemə yüklü olan original python3-ün üzərinə yazdığınız üçün, 10 proyektdən birini production serverə atdığınızda migrasiya zamanı vaxt baxımından problemlər çıxacaq.

Bunları problemi həll etmək məqsədi ilə virtual  environmentlər istifadə olunur. Virtual environmentlərdən istifadə edərən, hər proyektin içində özünə lazım olan paketləri saxlayan bir virtual mühit olduğu üçün, siz proyekti başqa bir serverə atdıqdan sonra sadəcə həmin virtual mühiti aktivləşdirərək bütün miqrasiya problemlərindən azad ola bilərsiniz.
{% endhint %}

Sistemə virtual environmenti yükləmək üçün:

```text
$ sudo -H pip3 install -U pipenv
```

Proyektim üçün yeni bir qovluq yaradıram:

```text
$ mkdir ~/Documents/yeniproyekt -p
$ cd ~/Documents/yeniproyekt
```

Hal-hazırda hansı qovluğun içində olduğum sizə maraqlıdırsa:
```text
$ pwk
```

Djangonu virtual mühitə yükləmək üçün:

```text
$ pipenv install django==2.2.5
```

Yuxarıdakı komandanı icra etdikdən sonra, görürəm ki, olduğum qovluda 2 fayl yarandı.

```text
$ ls
Pipfile    Pipfile.lock
```

Virtual mühiti aktivləşdirmək üçün:

```text
$ pipenv shell
```

`yeniproyekt` qovluğunun içində olduğumuz üçün, bizə terminalda `(yeniproyekt)` göstərdi.

Gəlin python3 interaktiv pəncərəsini açıb aşağıdakı əmrləri yazaraq djangonun versiyasını yoxlayaq.

```text
(yeniproyekt) $ python3
>>> import django
>>> print(django.get_version())
2.2.5 
```

Gördünüz kimi virtual mühitdə Djangonu quraşdırdıq.  
Bilməyənlər üçün deyim ki, python3-ün interaktiv pəncərəsindən `exit()` komandası ilə, virtual mühitdən isə `exit` komandası ilə çıxmaq mümkündür.

  
Təbriklər!  🥳   
Siz Djangonu sistemə quraşdırdınız. Bir sonrakı bölümə keçmək vaxtıdır! 😃 



