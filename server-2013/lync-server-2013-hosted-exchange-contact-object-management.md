﻿---
title: 'Lync Server 2013: управление объектом Contact в размещенной системе Exchange'
TOCTitle: Управление объектом Contact в размещенной системе Exchange
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412978(v=OCS.15)
ms:contentKeyID: 49311588
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Управление объектом Contact в размещенной системе Exchange в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-25_

Необходимо настроить контактный объект для каждого номера автосекретаря и кода доступа в распределенном развертывании.

Для интеграции с размещенной единой системой обмена сообщениями Exchange ocsumutil.exe не может использоваться для управления контактными объектами, поскольку оно зависит от параметров единой системы обмена сообщениями Exchange в Active Directory. В распределенном развертывании сервер Lync Server 2013 и размещенная единая система обмена сообщениями Exchange устанавливаются в разных лесах без отношений доверия между ними. В целях обеспечения безопасности администраторы сервера Lync Server 2013 не имеют прямого доступа к параметрам единой системы обмена сообщениями Exchange в Active Directory. В результате сервер Lync Server 2013 предоставляет другую модель для управления контактными объектами в *общем адресном пространстве SIP* , которое доступно как серверу Lync Server 2013, так и службе размещенной единой системы обмена сообщениями Exchange.

## Рабочий процесс размещенных контактных объектов

Далее приводятся общие действия для совместной работы с администратором клиента размещенного Exchange по управлению контактными объектами.

1.  Администратор Exchange запрашивает телефонные номера для доступа абонентов единой системы обмена сообщениями Exchange и контактные объекты автосекретаря.

2.  Администратор сервера Lync Server 2013 создает контактный объект для каждого телефонного номера и назначает политику размещенной голосовой почты каждому контактному объекту.

3.  Администратор сервера Lync Server 2013 предоставляет телефонные номера администратору Exchange.

4.  Администратор Exchange назначает эти телефонные номера соответствующим абонентским группам единой системы обмена сообщениями Exchange для автосекретарей и абонентского доступа.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Не требуется настраивать какие-либо параметры абонентских групп сервера Lync Server 2013 в контактных объектах, как это делается в распределенных развертываниях.</td>
</tr>
</tbody>
</table>


## Настройка размещенных контактных объектов

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Прежде чем контактные объекты сервера Lync Server 2013 можно будет включить для размещенной единой системы обмена сообщениями Exchange, необходимо развернуть политику размещенной голосовой почты, которая к ним применяется. Эта политика может быть задана на глобальном уровне, на уровне сайта или на уровне пользователя, если она применяется к контактному объекту, который требуется включить. Подробные сведения см. в статье <a href="lync-server-2013-hosted-voice-mail-policies.md">Политики размещенной голосовой почты в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


Для настройки размещенных контактных объектов автосекретаря и абонентского доступа в распределенном развертывании необходимо использовать следующие командлеты:

  - **New-CsExUmContact**, который создает новый контактный объект для размещенной единой системы обмена сообщениями;

  - **Set-CsExUmContact**, который изменяет существующий контактный объект для размещенной единой системы обмена сообщениями Exchange.

В следующем примере создается контактный объект автосекретаря:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

В этом примере создается новый контактный объект единой системы обмена сообщениями Exchange с SIP-адресом sip:exumaa1@fabrikam.com. Служба регистратора сервера Lync Server 2013 работает в пуле с именем RedmondPool.litwareinc.com. Сведения будут сохраняться в подразделении Active Directory OU=ExUmContacts,DC=litwareinc,DC=com. Телефонный номер контактного объекта – 2065554567. Дополнительный параметр -AutoAttendant $True указывает, что этот объект является контактным объектом автосекретаря. Значение False параметра -AutoAttendant (установленное по умолчанию) указывает контактный объект абонентского доступа.

Подробные сведения о командлетах New-CsExUmContact и Set-CsExUmContact см. в документации по командной консоли Командная консоль Lync Server.
