<base target="_blank">

<div dir="ltr" >



[**🇺🇸 English**](README.md)
</div>
<br>
<div align=center markdown="1">
 

![Hiddify Logo](https://user-images.githubusercontent.com/125398461/227777845-a4d0f86b-faa2-4f2b-a410-4aa5f68bfe19.png)

</div>

<div dir="ltr">
 <base target="_blank">


# سازنده سرور میانی هیدیفای
این اسکریپت روش‌های زیر را برای ایجاد یک تونل بین سرور میانی و سرور اصلی در اختیار شما قرار میدهد.
<div align=center>
 
`۱. IP-Tables`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`۲. GOST`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`۳. Dokodemo-Door`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`۴. HA-Proxy`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`۵. Socat`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</div>

## ⚙️ نصب و راه‌اندازی
برای ایجاد تانل در سرور رله خود، فقط باید دستور زیر را اجرا کنید.

```
bash -c "$(curl -L https://raw.githubusercontent.com/hiddify/hiddify-relay/main/install.sh)"
```
<div align=center>

 <img src="https://github.com/hiddify/hiddify-relay/assets/125398461/3772cf2d-2898-497e-a3de-b72ac814d087" alt="Relay-builder Menu" />
</div>

### 🛠️ تانل IP-Tables 
طبق تصویر اول بالا، گزینه `1` را وارد کنید تا بتوانید `IP-Tables tunnel` را مدیریت کنید.

<div align=center>

![IP-Tables Tunnel Menu](https://github.com/hiddify/hiddify-relay/assets/125398461/da9b8dd7-8cb8-4ad6-963a-80d790f26d1a)

</div>
<div align="right">
 
`1. Install iptables rules`

بعد از انتخاب گزینه `1` در `IP-Tables Menu`، آیپی مربوط به سرور اصلی را باید وارد کنید تا تانل روی پورت‌های `443` و `80` فعال گردد.

`2. Check ports in use`

این گزینه به شما پورت‌های مورد استفاده در تانل IP-Tables را نشان می‌دهد.

`3. Uninstall iptables rules`

این گزینه همه قواعد ایجاد شده در IP-Tables را پاک می‌کند.

> [نکته!]
> 
> دقت داشته باشید که اگر قواعد خاصی در کنار تانل به صورت دستی ایجاد کرده باشید با این دستور پاک خواهند شد.

`4. Back to Main Menu`

به منظور بازگشت به منوی اصلی عدد `4` را وارد نمایید.


### 🛠️ تانل GOST
طبق تصویر اول بالا، گزینه `2` را وارد کنید تا بتوانید `GOST tunnel` را مدیریت کنید.

<div align=center>
 
![GOST Tunnel](https://github.com/hiddify/hiddify-relay/assets/125398461/fe813676-52e6-451f-8d78-22ebdfe2753e)

</div>

`1. Install GOST`

- پس از انتخاب گزینه `1`، منتظر بمانید تا تانل نصب شود.
- بعد از اتمان نصب، در قدم اول می‌بایست پورت‌های مورد نظر برای تانل را وارد نمایید.
- سپس ساب‌دامین مربوط به سور راصلی را وارد کنید تا تانل آغاز به کار نماید.
- بعد از آغاز به کار تانل، پیغام `Gost tunnel is installed and activated` به رنگ سبز روی صفحه ظاهر می‌شود.


`2. Check GOST Port and Status`

بعد از انتخاب این گزینه، پورت‌های مورد استفاده و وضعیت تانل روی صفحه نمایش داده می‌شود.

`3. Add Another Port and Domain`
- از این گزینه برای اتصال سرور میانی به چندین سرور خارجی می‌توان استفاده نمود.
- بعد از انتخاب گزینه `3`، می‌بایست پورت جدید و دامنه مربوط به سرور اصلی را وارد نمایید.
- برای اطمینان از انجام صحیح این کار می‌توان از گزینه `2` استفاده نمود و پورت‌ها و وضعیت تانل را طبق این گزینه چک نمود.


`4. Uninstall GOST`

با استفاده از این گزینه می‌توان تانل GOST را از سرور میانی حذف نمود.

`5. Back to Main Menu`

به منظور بازگشت به منوی اصلی عدد `5` را وارد نمایید.



### 🛠️ Dokodemo-door Tunnel
طبق تصویر اول بالا، گزینه `3` را وارد کنید تا بتوانید `Dekodemo-Door tunnel` را مدیریت کنید.

<div align=center>
 
![Dokodemo Tunnel](https://github.com/hiddify/hiddify-relay/assets/125398461/287db74b-cb88-4976-826e-5fcf5de99bfe)

</div>

`1. Install Xray and add inbound`
- بعد از انتخاب گزینه `1` در این منو، منتظر بمانید تا هسته Xray روی سرور میانی نصب گردد.
- بعد از اتمام نصب، آیپی آدرس یا دامنه مربوط به سرور اصلی را وارد نمایید.
- در بخش مربوط به پورت‌ها، پورت‌های مورد نظر خود برای ایجاد تانل را وارد نمایید. (پیشنهادی: 443,80)
- در انتها پیغام `Inbound added and tunnel started` روی صفحه ظاهر می‌شود که به معنی موفقیت آمیز بودن عملیات است.


`2. Check Xray Service Status`

با انتخاب گزینه `2`، پورت‌های مورد استفاده و وضعیت تانل روی صفحه نمایش داده می‌شود.

`3. Add another inbound`
- با انتخاب گزینه `3` در منوی تانل Dokodemo-Door، می‌توان کانکشن اینباند دیگری را برای اتصال سرور میانی به یک سرور خارجی دیگر تنظیم نمود.
- بعد از انتخاب گزینه `3`، می‌ایست آیپی آدرس یا دامنه مربوط به سرور اصلی جدید را وارد نمایید.
- در قدم بعد، پورت مربوط به این سرور وارد نمایید.
- وقتی پیغام `Additional inbound added` ظاهر شد، یعنی ایباند جدید اضفه شده است.
- برای چک کردن و حصول اطمینان از صحت انجام این مرحله می‌توان از گزینه `2` مطابق با گزینه قبل استفاده نمود و پورت‌ها و وضعیت تانل را چک نمود.



`4. Uninstall Xray and Dokodemo-Door tunnel`

از گزینه `4` برای حذف تانل Dokodemo-Door و هسته Xray از سرور میانی می‌توان استفاده نمود.

`5. Back to Main Menu`

به منظور بازگشت به منوی اصلی عدد `5` را وارد نمایید.


### 🛠️ HA-Proxy Tunnel
طبق تصویر اول بالا، گزینه `4` را وارد کنید تا بتوانید `HA-Proxy tunnel` را مدیریت کنید.

<div align=center>

 ![HA-Proxy Tunnel](https://github.com/hiddify/hiddify-relay/assets/125398461/af49cad2-a3fb-4870-9cea-ad0c7b99305c)

</div>

`1. Install HA-Proxy`
- بعد از انتخاب گزینه `1`، منتظر بمانید تا پکیج مربوط به HA-Proxy نصب گردد.
- بعد از نصب، در بخش پورت مربوط به Relay server، پورت مورد نظر خود برای سرور میانی را وارد نمایید. (پیشنهادی: 443)
- سپس آیپی آدرس مربوط به سرور اصی را وارد نمایید.
- در مرحله بعد، پورت مربوط به سرور اصلی وارد نمایید. ( به عنوان مثال `هیدیفای‌منیجر` از پورت‌ 443 استفاده می‌کند)
- بعد از اتمام این مرحل، در صورت نمایش پیغام `HA-Proxy tunnel is installed and activated` تانل به درستی نصب و راه‌اندازی شده است.


`2. Check HA-Proxy Ports and Status`

با انتخاب گزینه `2`۷ می‌توان پورت‌های در حال استفاده و وضعیت تانل را چک نمود.



`3. Uninstall HA-Proxy`

برای حذف تانل HA-Proxy از سرور میانی از این گزینه استفاده نمایید.

`4. Back to Main Menu`
به منظور بازگشت به منوی اصلی عدد `4` را وارد نمایید.



### 🛠️ Socat Tunnel
طبق تصویر اول بالا، گزینه `5` را وارد کنید تا بتوانید `Socat tunnel` را مدیریت کنید.

<div align=center>

 ![Socat Tunnel](https://github.com/hiddify/hiddify-relay/assets/125398461/d0d55310-f06d-44f2-83df-9b698ee9d0fa)

</div>

`1. Install Socat And Setup Tunnel Service`

- با انتخاب گزینه `1` منتظر بمانید تا پکیج Socat نصب شود.
- سپس آیپی و پورت مربوط به سرور اصلی را وارد نمایید.
- بعد از انجام صحیح عملیات، با ظاهر شدن پیغام `Socat tunnel is installed and activated، تانل به درستی فعال می‌شود.

  
`2. Check Socat Port`

با انتخاب گزینه `2` می‌توان پورت‌های مورد استفاده و وضعی تانل را چک نمود.


`3. Uninstall Socat And Remove Tunnel Service`

با انتخاب این گزینه می توان تانل Socat را از سرور میانی حذف نمود.


`4. Back To Main Menu`
به منظور بازگشت به منوی اصلی عدد `4` را وارد نمایید.

<br>

> [نکته!]
> 
> اگر می‌خواهید سرور میانی خود را به `هیدیفای‌منیجر` متصل نمایید، این [مقاله](https://github.com/hiddify/Hiddify-Manager/wiki/%D9%86%D8%AD%D9%88%D9%87-%D8%A7%D9%81%D8%B2%D9%88%D8%AF%D9%86-%D8%B3%D8%B1%D9%88%D8%B1-%D9%85%DB%8C%D8%A7%D9%86%DB%8C-%D8%A8%D9%87-%D9%87%DB%8C%D8%AF%DB%8C%D9%81%D8%A7%DB%8C-%D9%85%D9%86%DB%8C%D8%AC%D8%B1) را مطالعه نمایید.


<div align=center>

<br>

***

[![Email](https://img.shields.io/badge/Email-contribute@hiddify.com-005FF9?style=flat-square&logo=mail.ru)](mailto:contribute@hiddify.com)
[![Telegram Channel](https://img.shields.io/endpoint?label=Channel&style=flat-square&url=https%3A%2F%2Ftg.sumanjay.workers.dev%2Fhiddify&color=blue)](https://telegram.dog/hiddify)
[![Telegram Group](https://img.shields.io/endpoint?color=neon&label=Support%20Group&style=flat-square&url=https%3A%2F%2Ftg.sumanjay.workers.dev%2Fhiddify_board)](https://telegram.dog/hiddify_board)
[![Youtube](https://img.shields.io/youtube/channel/views/UCxrmeMvVryNfB4XL35lXQNg?label=Youtube&style=flat-square&logo=youtube)](https://www.youtube.com/@hiddify)
[![Twitter](https://img.shields.io/twitter/follow/hiddify_com?color=%231DA1F2&logo=twitter&logoColor=1DA1F2&style=flat-square)](https://twitter.com/intent/follow?screen_name=hiddify_com)

</div>

<p align=center>
 We appreciate all people who are participating in this project. Some people here and many many more outside of Github. It means a lot to us. ♥
 </p>
 
<p align=center> 
<a href="https://github.com/hiddify/hiddify-relay/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=hiddify/hiddify-relay" />
</a>
</p>
<p align=center>
 Made with <a rel="" target="_blank" href="https://contrib.rocks">Contrib.Rocks</a> 
</p>
