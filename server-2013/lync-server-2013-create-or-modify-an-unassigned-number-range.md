﻿---
title: 'Lync Server 2013: создание или изменение диапазона неназначенных номеров'
TOCTitle: Создание или изменение диапазона неназначенных номеров
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412748(v=OCS.15)
ms:contentKeyID: 49310704
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение диапазона неназначенных номеров в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

Используйте одну из следующих процедур для настройки диапазонов неназначенных телефонных номеров для "Объявление".

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Перед настройкой таблицы неназначенных номеров требуется определить оповещения или настроить автосекретарь единой системы обмена сообщениями Exchange.</td>
</tr>
</tbody>
</table>


## Использование управления Lync Server для настройки неназначенных телефонных номеров

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Функции голосовых служб** , а затем выберите **Неназначенный номер** .

4.  На странице **Неназначенный номер** выполните одно из следующих действий:
    
      - Чтобы создать новый диапазон номеров, выберите **Создать** . В поле **Имя** введите имя для этого диапазона номеров.
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>После записи нового диапазона неназначенных номеров в базе данных вы не сможете изменить имя диапазона.</td>
        </tr>
        </tbody>
        </table>
    
      - Чтобы изменить существующий диапазон номеров, введите его имя целиком (или же его часть) в поле поиска. В списке найденных диапазонов номеров щелкните нужное имя, выберите **Изменить** , аз щелкните **Подробнее** .

5.  В первом поле **Диапазон номеров** введите первый номер диапазона, а во втором поле **Диапазон номеров** введите последний номер диапазона.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><ul>
    <li><p>Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</p></li>
    <li><p>Если первый номер или последний номер диапазона содержит добавочный номер, то оба номера (первый и последний) должны содержать добавочный номер. Кроме того, добавочный номер должен быть одинаковым для первого и последнего номера диапазона.</p></li>
    <li><p>Номер должен соответствовать регулярному выражению (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?. Это означает, что номер должен начинаться со строки &quot;tel:&quot; (если эта строка не указана, она будет добавлена автоматически), знака &quot;плюс&quot; (+) и цифры от 1 до 9. Номер телефона может быть длиной до 17 цифр, и в конце может быть указан добавочный номер в формате &quot;;ext=добавочный_номер&quot;.</p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>


6.  В поле **Служба оповещения** выполните одно из следующих действий:
    
      - Щелкните **Оповещение** .
    
      - Щелкните **Единая система обмена сообщениями Exchange** .

7.  Если на предыдущем шаге вы выбрали **Оповещение** , выполните следующие действия:
    
    1.  В **Полное доменное имя конечного сервера** щелкните **Выбор** , щелкните ИД службы приложения, запускающей приложение "Объявление", которое будет обрабатывать входящие вызовы для этого диапазона неназначенных номеров, и затем нажмите кнопку **ОК** .
    
    2.  В списке **Оповещение** выберите оповещение, воспроизводимое для этого диапазона неназначенных номеров.

8.  Если на предыдущем шаге вы выбрали **Единая система обмена сообщениями Exchange** , то в **Номер автосекретаря** щелкните **Выбор** , выберите номер телефона, используемый для этого диапазона неназначенных номеров, и затем нажмите кнопку **ОК** .

9.  Нажмите кнопку **ОК** .

10. Убедитесь, что на странице **Неназначенный номер** диапазоны неназначенных номеров расположены в требуемом порядке. Чтобы изменить расположение диапазона в таблице, выберите одно или несколько смежных имен в списке диапазонов, а затем щелкните стрелки вверх или вниз.
    

    > [!TIP]
    > Lync Server просматривает таблицу неназначенных номеров сверху вниз и использует первый диапазон, который соответствует неназначенному номеру. При наличии перекрывающихся диапазонов и одного диапазона, который задает последнее возможное действие, убедитесь, что этот диапазон находится внизу списка.



11. Если диапазоны неназначенных номеров расположены в требуемом порядке, щелкните **Фиксировать все** .

## Использование Windows PowerShell для настройки неназначенных телефонных номеров

1.  Войдите на компьютер, где установлена командная консоль Lync Server, как член группы RTCUniversalServerAdmins или имея необходимые права пользователя, описанные в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Используйте **New-CsUnassignedNumber** для создания нового диапазона неназначенных номеров. Используйте **Set-CsUnassignedNumber** для изменения существующего диапазона неназначенных номеров.
    

    > [!TIP]
    > Если имеются перекрывающиеся диапазоны и требуется, чтобы эти диапазоны применялись в определенном порядке, включите параметр Priority. В этом случае при звонке будет применяться диапазон, обладающий наибольшим приоритетом.

    
    В командной строке выполните один из следующих действий:
    
      - Чтобы создать диапазон номеров для службы оповещения, выполните:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Или: чтобы создать диапазон номеров для автосекретаря единая система обмена сообщениями Exchange, выполните:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Например:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Или
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    В следующем примере показывается, как можно изменить номера в существующем диапазоне неназначенных номеров:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## См. также

#### Задачи

[Удаление диапазона неназначенных портов в Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  

#### Другие ресурсы

[New-CsUnassignedNumber](new-csunassignednumber.md)  
[Set-CsUnassignedNumber](set-csunassignednumber.md)  
[Get-CsUnassignedNumber](get-csunassignednumber.md)
