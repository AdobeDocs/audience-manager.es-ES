---
description: Envíe datos a la API de DCS utilizando métodos GET o POST.
seo-description: Envíe datos a la API de DCS utilizando métodos GET o POST.
seo-title: Métodos de API de DCS
solution: Audience Manager
title: Métodos de API de DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS API Methods {#dcs-api-methods}

Send data to the [!UICONTROL DCS] [!DNL API] using `GET` or `POST` methods.

You can send data to the [!UICONTROL DCS] using either one of the `GET` or `POST` methods. Take a look at the sample calls below, using [curl](https://curl.haxx.se/). In all three sample calls, we are adding the signals `c_likes = famous popstar` and `c_loves = famous actress` to the device profile `12345678901234567890123456789012345678`.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Send Data via GET {#send-data-via-get}

Note that the maximum allowed size for `GET` calls is 8K.

<pre><code>curl -i "<i>yourcompany.demdex.net/event</i>?
d_uuid=<i>12345678901234567890123456789012345678</i>&amp;d_rtbd=json&amp;<i>c_likes=famous%20popstar</i>&amp;<i>c_loves=famous%20actress</i>"
</code></pre>

## Send Data via POST {#send-data-via-post}

Note the requirements for sending data using the `POST` method:

* El tamaño máximo permitido es 32 K.
* Set the content type to `application/x-www-form-urlencoded`.

### Llamada de muestra

<pre><code>curl -x POST\ 
 https://yourcompany.demdex.net/event<i></i>\ 
 -h'content-type: application/x-www-form-urlencoded '\ 
 -d'<i>c_ like = fam% 20 popstar</i>&amp;<i>c_ loves = famoso % 20 actriz</i>&amp;<i>d_ uuid = 12345678901234567890123456789012345678</i>'</code>
</pre>

<pre><code>curl -x POST\ 
 https://yourcompany.demdex.net/event<i></i>\ 
 -h'content-type: application/x-www-form-urlencoded '\ 
 -d'<i>c_ like = fam% 20 popstar</i>&amp; <i>c_ loves = famoso % 20 actriz</i>&amp;<i>d_ uuid = 12345678901234567890123456789012345678</i>'</code>
</pre>
