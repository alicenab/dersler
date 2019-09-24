---
description: >-
  Django-nu necə hazırlamalı sualını 100 nəfərə versəniz 101 fərqli cavab
  alacaqsınız. Mənim cavabım:
---

# Mühitin hazırlanması

## Quraşdırılma

İstifadəçilər Djangonu quraşdırarkən fərqli xətalarla qarşılaşa bilirlər. Bunların qarşısını almaq üçün bu dərsdə hamının mühitinin eyni olmasına çalışacağam.  
Öz mühitimizi Ubuntu üzərində quracayıq. Virtual serverə quracağımız ubuntu.iso faylını aşağıdaki linkdən yükləyə bilərsiniz.

```bash
wget http://releases.ubuntu.com/18.04.3/ubuntu-18.04.3-live-server-amd64.iso
```

{% hint style="warning" %}
Django istifadəsi üçün Python3 məsləhət görülür çünki Python2.7-yə olan dəstək 2020-ci ildə bitəcək. Nəzərə alsaq ki, Ubuntu 18.04 özü ilə birlikdə python3 də yükləyir. Bu baxımdan bizim üçün problem olmayacaq.
{% endhint %}

Virtual Serverdə Ubuntunu əlavə paketlər olmadan \(installing prosesində sondaki paketləri seçmədən\) pure şəkildə quraşdırdım. Virtual maşında snapshot aldım ki, hər hansı problem ilə qarşılaşdığımda əvvəlki vəziyyətə qayıda bilim. 😌

Serverə yüklənmiş Python iki cür görsənmək ehtimalı var, python və python3. Sadə dildə desək, python 2.x versiyaları üçün, python3 isə python 3.x versiyaları üçün nəzərdə tutulub. Sistemə yüklənib yüklənmədiyini aşağıdakı qaydada yoxlamalıyıq:

```bash
$ python --version
Python 2.7.15+
$ python3 --version
Python 3.6.8
```

Gördünüz kimi iki fərqli python yüklüdür. Python komandalarından istifadə edərkən python3.x seriyalarından istifadə etmək istədiyimiz üçün aşağıdaki komandanı daxil edirik:

```bash
$ alias python=python3
$ python --version
Python 3.4.3
```

Alias komandasının köməyi ilə, biz çaşıb python yazdığımızda belə python3-ü çağırmış olacayıq.

{% hint style="info" %}
Bu əməliyyatı geri qaytarmaq üçün, aşağıdakı kimi `unalias`komandasını icra edə bilərsiniz.  
Gördüyünüz kimi yenidən `python --version` komandasını işlətdiyimizdə bizə əvvəlki nəticəni verdi.

```bash
$ unalias python
$ python --version
Python 2.7.6
```
{% endhint %}

Rəsmi dokumentasiya tərəfindən Django üçün məsləhət görülən quraşdırılma metodu `pip` vasitəsiylədir. Python3-ə aid olan pip versiyası pip3-dür. Serverə pip3 quraşdırmaq üçün:

```bash
$ sudo apt install python3-pip
```

{% hint style="info" %}
Nəzərinizə çatdıırm ki, pip3 python3-ə aid olduğu üçün, yazıda çaşmayaq deyə yuxarıda etdiyim kimi alias əlavə etdim.

```bash
$ alias pip=pip3
```
{% endhint %}

Sistemə Django quraşdırmaq üçün aşağıdakı komandanı daxil edirik:

```bash
$ pip install Django
```

Sistemə Djangonun yükləndiyini aşağıdakı komanda ilə təsdiqləyək:

```bash
$ python -m django --version
2.2.5
```

Təbriklər! Siz Djangonu sistemə quraşdırdınız. Bir sonrakı bölümə keçmək vaxtıdır! 😃

