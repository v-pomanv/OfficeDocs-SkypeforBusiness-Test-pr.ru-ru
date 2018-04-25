﻿---
title: Сводка по сертификатам — автообнаружение
TOCTitle: Сводка по сертификатам — автообнаружение
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ945616(v=OCS.15)
ms:contentKeyID: 52058168
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Сводка по сертификатам — автообнаружение

 

_**Дата изменения раздела:** 2015-03-09_

Служба автообнаружения Lync Server 2013 выполняется на серверах пула директоров и интерфейсного пула, а при публикации в DNS она может использоваться клиентами Lync для определения расположения сервера и служб обслуживания пользователей. Если вы выполняете обновление с Lync Server 2010 и не развернули Mobility Service, то для использования клиентами функции автоматического обнаружения следует изменить списки альтернативных имен субъекта сертификатов в каждом Директоре и на каждом сервере переднего плана, где выполняется служба автообнаружения. Кроме того, может потребоваться изменить списки альтернативных имен субъектов для сертификатов, используемых для правил публикации внешних веб-служб на обратных прокси-серверах.

Решение об использовании списков альтернативных имен субъектов на обратных прокси-серверах основано на том, публикуете ли вы службу автоматического обнаружения через порт 80 или через порт 443:

  - **Публикация через порт 80.** Если начальный запрос в службу автоматического обнаружения выполняется через порт 80, изменения сертификата не требуются. Это вызвано тем, что мобильные устройства с запущенным продуктом Lync осуществят доступ к обратному прокси-серверу через порт 80 извне, а затем с использованием моста будут перенаправлены в Директор или на сервер переднего плана через порт 8080 внутренними средствами. Дополнительные сведения см. в разделе "Первоначальный процесс автообнаружения с использованием порта 80" статьи [Технические требования для организации мобильной работы в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Публикация через порт 443.** Список альтернативных имен субъектов для сертификатов, используемых правилом публикации внешних веб-служб, должен содержать запись *lyncdiscover.\<домен\_sip\>* для каждого домена SIP в вашей организации.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Мы настоятельно рекомендуем использовать HTTPS вместо HTTP. Протокол HTTPS применяет сертификаты для шифрования трафика. Протокол HTTP не обеспечивает шифрование, и все данные отправляются в виде обычного текста.</td>
    </tr>
    </tbody>
    </table>


Повторная выдача сертификатов с использованием внутреннего центра сертификации обычно не вызывает трудностей. Но для общих сертификатов, используемых для правила публикации внешних веб-служб, добавление нескольких записей альтернативных имен субъектов может оказаться дорогостоящим. Чтобы решить данную проблему, мы поддерживаем начальное подключение автоматического обнаружения через порт 80, с которого потом выполняется переадресация на порт 8080 Директора или сервера переднего плана.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если в инфраструктуре Lync Server 2013 используются внутренние сертификаты, которые выдает внутренний центр сертификации (CA), и вы планируете поддерживать мобильные устройства, подключающиеся по беспроводной сети, нужно установить на мобильных устройствах корневую цепочку сертификатов от внутреннего CA или перейти на общедоступный сертификат в вашей инфраструктуре Lync Server 2013.</td>
</tr>
</tbody>
</table>


В данном разделе описываются добавленные альтернативные имена субъекта, которые необходимы для Директора, сервера переднего плана и обратного прокси-севера. Данная информация касается только добавленных альтернативных имен субъекта (SAN). Для получения сведений о других записях сертификатов обратитесь к разделам по планированию. Дополнительные сведения см. в статьях [Сценарии для директора в Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) и [Сценарии для обратного прокси-сервера в Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

В следующих таблицах определяются записи SAN автообнаружения для пула Директоров, пула переднего плана и обратного прокси-сервера:

### Требования к сертификатам пула Директоров

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внутренней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;внутреннее_имя_домена&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>URL-адрес внешней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;домен_SIP&gt;</em></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Обновленный сертификат с новой записью SAN назначается сертификату по умолчанию. Или же можно использовать строку SAN=*.<em>&lt;домен_SIP&gt;</em>.</td>
</tr>
</tbody>
</table>


### Требования к сертификатам интерфейсного пула

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внутренней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;внутреннее_имя_домена&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>URL-адрес внешней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;домен_SIP&gt;</em></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Обновленный сертификат с новой записью SAN назначается сертификату по умолчанию. Или же можно использовать строку SAN=*.<em>&lt;домен_SIP&gt;</em></td>
</tr>
</tbody>
</table>


### Требования к сертификатам обратного прокси-сервера (общедоступный ЦС)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Описание</th>
<th>Запись альтернативного имени субъекта</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL-адрес внешней службы автообнаружения</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;домен_SIP&gt;</em></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Обновленный сертификат с новой записью SAN назначается прослушивателю SSL на обратном прокси-сервере.</td>
</tr>
</tbody>
</table>
