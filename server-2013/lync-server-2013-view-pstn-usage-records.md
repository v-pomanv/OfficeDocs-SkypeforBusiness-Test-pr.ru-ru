﻿---
title: 'Lync Server 2013: просмотр записей использования ТСОП'
TOCTitle: Просмотр записей использования ТСОП
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398458(v=OCS.15)
ms:contentKeyID: 49309999
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Просмотр записей использования ТСОП в Lync Server 2013

 

_**Дата изменения раздела:** 2013-02-22_

В записи об использовании ТСОП указывается класс вызова (например, внутренний, локальный вызов или вызов на дальние расстояния), который может выполняться различными пользователями или группами пользователей в организации. Для получения дополнительных сведений см. [Записи использования ТСОП в Lync Server 2013](lync-server-2013-pstn-usage-records.md) в **документации** по планированию.

## Просмотр записи об использовании ТСОП с помощью управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см. в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Маршрутизация голосовой связи** , а затем щелкните **Использование ТСОП** .

4.  На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка** , а затем щелкните **Показать подробности** .
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи.</td>
    </tr>
    </tbody>
    </table>


## Просмотр сведений об использовании ТСОП с помощью командлетов Windows PowerShell

Также можно просмотреть записи об использовании ТСОП с помощью Windows PowerShell и командлета **Get-CsPstnUsage**. Этот командлет можно запустить либо из командная консоль Lync Server 2013, либо из удаленного сеансаWindows PowerShell. Дополнительные сведения об использовании Windows PowerShell в удаленном режиме для подключения к Lync Server см. статью блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 в удаленном режиме с помощью PowerShell" по адресу [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Просмотр сведений об использовании ТСОП с помощью командлетов Windows PowerShell

  - Чтобы просмотреть сведения об использовании ТСОП, введите следующую команду в командной консоли Командная консоль Lync Server и нажмите клавишу ВВОД:
    
        Get-CsPstnUsage
    
    Этой командой возвращается информация, аналогичная следующим сведениям:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

Подробнее см. [Get-CsPstnUsage](get-cspstnusage.md).

## См. также

#### Задачи

[Создание голосовой политики и настройка записей использования ТСОП в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Изменение голосовой политики и настройка записей использования ТСОП в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)
