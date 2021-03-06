﻿---
title: Исключения IPsec в Lync Server 2013
TOCTitle: Исключения IPsec в Lync Server 2013
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg425719(v=OCS.15)
ms:contentKeyID: 49309207
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Исключения IPsec в Lync Server 2013

 

_**Дата изменения раздела:** 2015-03-09_

Для корпоративных сетей, где развернут протокол IPSec (см. документ IETF RFC 4301-4309), необходимо отключить IPSec для диапазона портов, используемых для доставки аудио, видео и панорамного видео. Это связано с необходимостью избежать каких-либо задержек при распределении портов мультимедиа из-за согласования IPsec.

В следующей таблице описаны рекомендуемые исключения IPsec.

### Рекомендуемые исключения IPsec

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя правила</th>
<th>Исходный IP-адрес</th>
<th>Конечный IP-адрес</th>
<th>Протокол</th>
<th>Исходный порт</th>
<th>Конечный порт</th>
<th>Требование проверки подлинности</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Внутренние входящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>Внутренние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Внешние входящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>Внешние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Внутренние исходящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Внутренние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Внешние исходящие данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Внешние данные пограничного сервера аудио- и видеоданных</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные сервера-посредника</p></td>
<td><p>Любой</p></td>
<td><p>Посредник</p>
<p>Серверы</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные сервера-посредника</p></td>
<td><p>Посредник</p>
<p>Серверы</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные помощника по конференц-связи</p></td>
<td><p>Любой</p></td>
<td><p>Интерфейсный сервер с помощником по конференц-связи</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные помощника по конференц-связи</p></td>
<td><p>Интерфейсный сервер с помощником по конференц-связи</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные аудио- и видеоконференций</p></td>
<td><p>Любой</p></td>
<td><p>Интерфейсные серверы</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные аудио- и видеоконференций</p></td>
<td><p>Интерфейсные серверы</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Входящие данные Exchange</p></td>
<td><p>Любой</p></td>
<td><p>Единая система обмена сообщениями Exchange</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Входящие данные серверов совместного использования приложений</p></td>
<td><p>Любой</p></td>
<td><p>Серверы совместного использования приложений</p></td>
<td><p>TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Исходящие данные серверов совместного использования приложений</p></td>
<td><p>Серверы совместного использования приложений</p></td>
<td><p>Любой</p></td>
<td><p>TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="even">
<td><p>Исходящие данные Exchange</p></td>
<td><p>Единая система обмена сообщениями Exchange</p></td>
<td><p>Любой</p></td>
<td><p>UDP и TCP</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
<tr class="odd">
<td><p>Клиенты</p></td>
<td><p>Любой</p></td>
<td><p>Любой</p></td>
<td><p>UDP</p></td>
<td><p>Указанный диапазон портов мультимедиа</p></td>
<td><p>Любой</p></td>
<td><p>Не выполнять проверку подлинности</p></td>
</tr>
</tbody>
</table>

