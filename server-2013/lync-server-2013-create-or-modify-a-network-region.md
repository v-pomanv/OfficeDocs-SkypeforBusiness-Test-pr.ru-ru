﻿---
title: 'Lync Server 2013: создание или изменение сетевой области'
TOCTitle: Создание или изменение сетевой области
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412933(v=OCS.15)
ms:contentKeyID: 49311016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание или изменение сетевой области в Lync Server 2013

 

_**Дата изменения раздела:** 2012-10-19_

*Области сети* представляют сетевые концентраторы или магистрали, используемые при настройке контроля допуска звонков, службы E9-1-1 и обхода сервера-посредника. Для создания и изменения областей сети используйте процедуры, описанные в этом разделе. Например, если вы уже создали области сети для одной функции голосовой связи, то вам не потребуется создавать новые области сети, поскольку остальные функции корпоративной голосовой связи будут использовать имеющиеся области сети. Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции. Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт. Дополнительные сведения см. в разделе [Настройка сетевых областей для контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Все требования к определениям областей сети, относящиеся к функциям, приведены в разделах, посвященных развертываниям функций.</td>
</tr>
</tbody>
</table>


Дополнительные сведения о работе с областями сети см. в документации Командная консоль Lync Server по следующим командлетам:

  - [New-CsNetworkRegion](new-csnetworkregion.md)

  - [Get-CsNetworkRegion](get-csnetworkregion.md)

  - [Set-CsNetworkRegion](set-csnetworkregion.md)

  - [Remove-CsNetworkRegion](remove-csnetworkregion.md)

## Создание области сети

Создание области сети, которая может использоваться службой контроля допуска звонков, службой E9-1-1 или при обходе сервера-посредника.

## Создание области сети с помощью Командная консоль Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать области сети, используйте командлет New-CsNetworkRegion.
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Например:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    В этом примере показано создание области сети "NorthAmerica", которая связана с центральным сайтом с ИД CHICAGO.

3.  Чтобы завершить создание областей сети для вашей топологии, повторите шаг 2, указав требуемые параметры для каждой области сети.

## Создание области сети с помощью командной консоли панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети** .

3.  Щелкните **Region** (Область).

4.  Щелкните **Создать** .

5.  На странице **New Region** (Создание области) введите имя области сети в поле **Name** (Имя).

6.  Щелкните **Central site** (Центральный сайт) и затем выберите центральный сайт в списке.

7.  В поле **Description** (Описание) введите дополнительные сведения об области сети (необязательно).

8.  Щелкните **Исполнить** .

9.  Чтобы завершить создание областей сети для вашей топологии, повторите шаги с 4 по 8, указав требуемые параметры для остальных областей.

## Изменение области сети

Изменение параметров существующей области сети в соответствии с изменениями основных сведений об области сети или требованиями новой функции.

## Изменение области сети с помощью Командная консоль Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы изменить существующую область сети, выполните командлет Set-CsNetworkRegion.
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Например:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    В этом примере показано изменение описания области сети "NorthAmerica", созданной ранее. Если для области "NorthAmerica" описание уже задано, оно будет перезаписано; в противном случае описание будет задано.

3.  Чтобы изменить остальные области сети, повторите шаг 2, указав параметры для остальных областей.

## Изменение области сети с помощью командной консоли панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети** .

3.  Нажмите кнопку навигации **Region** (Область).

4.  В таблице щелкните область сети, которую требуется изменить.

5.  Щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).

6.  На странице **Edit Region** (Изменение области) измените требуемые параметры области сети.

7.  Щелкните **Исполнить** .

8.  Чтобы завершить изменение областей сети, повторите шаги 4–7, используя параметры для других областей.
