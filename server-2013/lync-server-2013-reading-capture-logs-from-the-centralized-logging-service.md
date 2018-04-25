﻿---
title: Чтение записей журналов службы централизованного ведения журналов
TOCTitle: Чтение записей журналов службы централизованного ведения журналов
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49888184
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Чтение записей журналов службы централизованного ведения журналов

 

_**Дата изменения раздела:** 2016-12-28_

Вы понимаете реальное преимущество службы централизованная служба ведения журнала после запуска поиска и получения файла, который можно использовать для исследования сообщенной проблемы. Существует много способов чтения этого файла. Выходной файл имеет стандартный текстовый формат, и можно использовать Notepad.exe или любую другую программу, позволяющую открывать и читать текстовые файлы. Для больших файлов и более сложных проблем можно использовать такое средство, как Snooper.exe, разработанное для чтения и анализа выходных данных журнала, полученных из службы централизованная служба ведения журнала. Snooper входит в состав средств отладки Lync Server 2013, доступных в виде отдельной загрузки. Для средств отладки Lync Server 2013 не создаются ярлыки и пункты меню. После установки средств отладки Lync Server 2013 откройте проводник, окно командной строки или командную консоль Командная консоль Lync Server и перейдите в каталог (расположение по умолчанию) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools. Дважды щелкните программу Snooper.exe или введите Snooper.exe и нажмите клавишу ВВОД при использовании командной строки или командной консоли Командная консоль Lync Server.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В цели этого раздела не входит подробное обсуждение методов диагностики. Диагностика и сопутствующие процессы являются сложной темой. Подробные сведения об основах диагностики и особых рабочих процессах диагностики см. в книге набора ресурсов Microsoft Lync Server 2010 по адресу <a href="http://go.microsoft.com/fwlink/?linkid=211003%26clcid=0x419" class="uri">http://go.microsoft.com/fwlink/?linkid=211003&amp;clcid=0x419</a>. Процессы и процедуры по-прежнему применяются к Lync Server 2013.</td>
</tr>
</tbody>
</table>


В Lync Server 2013 появилась обновленная версия Snooper, включающая несколько новых функций. На следующем снимке экрана показана версия Snooper из Office Communications Server 2007.

![Версия Office Communications 2007 для Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Версия Office Communications 2007 для Snooper.")

На следующем снимке экрана показана новая версия Snooper, включенная в средства отладки Lync Server 2013.

![Версия Lync Server 2013 для Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Версия Lync Server 2013 для Snooper.")

На следующем снимке экрана показана панель инструментов с часто используемыми функциями.

![Панель управления Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Панель управления Snooper 2013.")

Новейшая функция, имеющая большое значение, это представление "Flow Chart (call flow)" ("Блок-схема (поток вызовов)"). Вы выбираете поток сообщений на вкладке **Message** (Сообщение) и нажимаете кнопку **Call Flow** (Поток вызовов). По мере прохода по сообщениям схема потока вызовов обновляется новыми данными.

![Схема вызова Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Схема вызова Snooper 2013.")

Вы можете навести курсор мыши на представление схемы и получить подробные сведения о сообщениях и контенте потоков и сообщений, а также о серверных элементах. Щелкните любую стрелку потока вызовов, чтобы перейти к сообщению в представлении сообщений.

![Сведения о сообщении со схемой вызова.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Сведения о сообщении со схемой вызова.")

## Открытие файла журнала в Snooper

1.  Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, необходимо быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.

2.  После установки средств отладки Lync Server (LyncDebugTools.msi) перейдите в каталог расположения Snooper.exe с помощью проводника или из командной строки. По умолчанию средства отладки размещаются в каталоге C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools. Дважды щелкните файл Snooper.exe или запустите его.

3.  После открытия Snooper щелкните правой кнопкой мыши пункт **File** (Файл), выберите пункт **Open File** (Открыть файл), найдите файлы журнала, выберите нужный файл в диалоговом окне **открытия файла** и нажмите кнопку **Open** (Открыть).

4.  Сообщения **трассировки** появятся на вкладке **Trace** (Трассировка). Щелкните вкладку **Messages** (Сообщения), чтобы просмотреть контент сообщений собранных трассировок.

## Отображение схемы потока вызовов

1.  Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, вы должны быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.

2.  Откройте файл журнала и перейдите на вкладку **Messages** (Сообщения); выберите беседу в представлении сообщений или выберите компонент трассировки на вкладке **Trace** (Трассировка).

3.  Нажмите **Call Flow** (Поток вызовов).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Если щелкнуть сообщение или трассировку, не являющуюся частью потока вызовов, то схема не появится, и внизу экрана Snooper появится сообщение о состоянии “This message is not eligible for callfow” (&quot;Это сообщение неприемлемо для потока вызовов&quot;). Выберите другое сообщение или трассировку, и если это сообщение или трассировка является частью потока вызовов, то появится поток вызовов.</td>
    </tr>
    </tbody>
    </table>


4.  Пройдите по строкам сообщений или трассировки и обратите внимание, отображают ли обновления или изменения схемы потока вызовов новую схему.

5.  Помещайте указатель мыши поверх элементов, чтобы получить сведения о сообщениях, конечных точках и других компонентах вызовов.
