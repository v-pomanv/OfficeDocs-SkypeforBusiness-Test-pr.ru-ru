﻿---
title: Подробный отчет о конференции
TOCTitle: Подробный отчет о конференции
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ204728(v=OCS.15)
ms:contentKeyID: 49309130
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Подробный отчет о конференции

 

_**Дата изменения раздела:** 2015-03-09_

Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.

## Доступ к подробному отчету по конференции

Подробный отчет по конференции можно открыть из следующих отчетов:

  - [Отчет по контролю допуска звонков в Lync Server 2013](lync-server-2013-call-admission-control-report.md) (щелкнув метрику сведений для конференции)

  - [Отчет по списку отказов в Lync Server 2013](lync-server-2013-failure-list-report.md) (щелкнув метрику конференции)

  - [Отчет по активности пользователей в Lync Server 2013](lync-server-2013-user-activity-report.md) (щелкнув метрику URI конференции)

Из подробного отчета по конференции вы можете получить доступ к [Диагностический отчет в Lync Server 2013](lync-server-2013-diagnostic-report.md), щелкнув метрику диагностического отчета (сведений).

## Фильтры

Нет. Вы не можете фильтровать подробный отчет по конференции.

## Метрики

В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.

### Метрики информации о конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Можете ли вы выполнить сортировку по этому элементу?</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Conference URI</strong> (URI конференции)</p></td>
<td><p></p></td>
<td><p>URI, назначенный конференции. Например:</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool FQDN</strong> (Полное доменное имя пула)</p></td>
<td><p></p></td>
<td><p>Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Start time</strong> (Время начала)</p></td>
<td><p></p></td>
<td><p>Дата и время начала конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong> (Организатор)</p></td>
<td><p></p></td>
<td><p>SIP-адрес пользователя, организовавшего конференцию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>End time</strong> (Время окончания)</p></td>
<td><p></p></td>
<td><p>Дата и время завершения конференции.</p></td>
</tr>
</tbody>
</table>


В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.

### Метрики участия в конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Можете ли вы выполнить сортировку по этому элементу?</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>User</strong> (Пользователь)</p></td>
<td><p></p></td>
<td><p>SIP-адрес пользователя, участвовавшего в конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Role</strong> (Роль)</p></td>
<td><p></p></td>
<td><p>Роль (например, выступающий) участника конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connectivity</strong> (Подключение)</p></td>
<td><p></p></td>
<td><p>Возможность подключения к сети (обычно изнутри или извне) для участника.</p></td>
</tr>
<tr class="even">
<td><p>Join time (Время присоединения)</p></td>
<td><p></p></td>
<td><p>Дата и время присоединения участника к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Leave time</strong> (Время ухода)</p></td>
<td><p></p></td>
<td><p>Дата и время покидания участником конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>User agent</strong> (Агент пользователя)</p></td>
<td><p></p></td>
<td><p>Идентификатор для программного обеспечения, используемого конечной точкой участника.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnostic reports</strong> (Диагностические отчеты)</p></td>
<td><p></p></td>
<td><p>Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</p></td>
</tr>
</tbody>
</table>


В следующей таблице приведены сведения из раздела модальностей конференции, входящего в подробный отчет по конференции.

### Метрики модальностей конференции

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Имя</th>
<th>Можете ли вы выполнить сортировку по этому элементу?</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>User</strong> (Пользователь)</p></td>
<td><p></p></td>
<td><p>SIP-адрес пользователя, участвовавшего в конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Join time</strong> (Время присоединения)</p></td>
<td><p></p></td>
<td><p>Дата и время присоединения участника к конференции.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Leave time</strong> (Время ухода)</p></td>
<td><p></p></td>
<td><p>Дата и время покидания участником конференции.</p></td>
</tr>
<tr class="even">
<td><p><strong>Conferencing server URI</strong> (URI сервера конференций)</p></td>
<td><p></p></td>
<td><p>URI для используемого в конференции сервера конференций.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnostic reports</strong> (Диагностические отчеты)</p></td>
<td><p></p></td>
<td><p>Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</p></td>
</tr>
</tbody>
</table>

