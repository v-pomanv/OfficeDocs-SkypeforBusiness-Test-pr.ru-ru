﻿---
title: Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013
TOCTitle: Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412840(v=OCS.15)
ms:contentKeyID: 49310850
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-05_

<table>
<thead>
<tr class="header">
<th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Если вы уже создали сетевые сайты для службы E9-1-1 или обхода сервера-посредника, то вы можете применить к ним профиль политики пропускной способности с помощью командлета <strong>Set-CsNetworkSite</strong>. Пример изменения сетевого сайта см. в разделе <a href="lync-server-2013-create-or-modify-a-network-site.md">Создание или изменение сетевого сайта в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


*Сетевые сайты* — это офисы или расположения в каждой области сети контроля допуска звонков, E9-1-1 и обхода сервера-посредника. Чтобы создать сетевые сайты, соответствующие примеру топологии сети для контроля допуска звонков, используйте следующие процедуры. В этих процедурах демонстрируется создание и настройка сетевых сайтов, на которые распространяется ограничение пропускной способности глобальной сети. Следовательно, для этих сетевых сайтов требуются политики пропускной способности, которые ограничивают трафик звуковых и видеоданных в режиме реального времени.

В примере развертывания контроля допуска звонков регион Северная Америка содержит 6 сайтов. На 3 сайта распространяется ограничение пропускной способности глобальной сети: Рино, Портленд и Альбукерке. На оставшиеся 3 сайта ограничение пропускной способности глобальной сети *не* действует: Нью-Йорк, Чикаго и Детройт. Пример создания или изменения сетевых сайтов см. в разделе [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Пример топологии сети см. в разделе [Пример: сбор своих требований организации для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) документации по планированию.

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В следующей процедуре для создания сетевого сайта используется Командная консоль Lync Server. Дополнительные сведения о создании сетевого сайта с помощью панели управления Lync Server см. в разделе <a href="lync-server-2013-create-or-modify-a-network-site.md">Создание или изменение сетевого сайта в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


## Создание сетевых узлов для контроля допуска звонков

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать сетевые сайты и применить требуемый профиль политики пропускной способности для каждого сайта, выполните командлет **New-CsNetworkSite**. Пример:
    
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
    
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
    
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link

3.  Чтобы завершить создание сетевых сайтов для всего примера топологии, повторите шаг 2 для сетевых сайтов с ограничением пропускной способности, расположенных в Европе, на Ближнем Востоке и в Африке, а также в Азиатско-тихоокеанском регионе.
