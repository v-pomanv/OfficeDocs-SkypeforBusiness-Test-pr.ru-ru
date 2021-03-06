﻿---
title: Перемещение оставшихся пользователей на Lync Server 2013
TOCTitle: Перемещение оставшихся пользователей на Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49888040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Перемещение оставшихся пользователей на Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-29_

Можно переместить пользователей в новое развертывание Lync Server 2013 с помощью управления Lync Server или Командная консоль Lync Server. Необходимо выполнить ряд требований, чтобы обеспечить органичный переход на Lync Server 2013. Сведения о предварительных требованиях, необходимых для завершения процедур, приведенных в данном разделе, см. в разделе [Настройка клиентов для миграции](configure-clients-for-migration.md). Подробное описание действий по перемещению пользователей см. в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).

> [!IMPORTANT]  
> Для перемещения пользователей из старой среды в Lync Server 2010 невозможно использовать оснастку &quot;Active Directory – пользователи и компьютеры&quot; или средства администрирования Lync Server 2013.

При перемещении пользователя в пул Lync Server 2013 данные пользователя перемещаются во внутреннюю базу данных, связанную с этим новым пулом.

> [!IMPORTANT]  
> Это относится к активным собраниям, созданным пользователем старой системы. Например, если этот пользователь настроил конференцию <strong>my meeting</strong> она будет доступна в новом пуле Lync Server 2013 после перемещения пользователя. Сведения для доступа к этому собранию – те же <strong>URL-адрес и код конференции</strong> . Единственное отличие заключается в том, что теперь конференция размещается в пуле Lync Server 2013, а не в пуле Lync Server 2010.

> [!NOTE]  
> Для размещения пользователей в Lync Server 2013 не требуется одновременного развертывания обновленных клиентов. Новые функциональные возможности станут доступными пользователям только после обновления до новой версии клиентского программного обеспечения.

## Задача после миграции

1.  После перемещения пользователей убедитесь, что для них назначена политика конференц-связи.

2.  Чтобы федеративные пользователи, размещенные в Lync Server 2013, могли работать с собраниями, которые были организованы пользователям, размещенными в Lync Server 2010, политика конференц-связи, назначенная для перенесенных пользователей, должна поддерживать анонимных участников.

3.  Для политик конференц-связи, поддерживающих анонимных участников, должны быть заданы следующие параметры: в панели управления Lync Server 2013 должен быть установлен флажок **Разрешить участникам приглашать анонимных пользователей** , а для атрибута **AllowAnonymousParticipantsInMeetings** при отображении выходных данных командлета **Get-CsConferencingPolicy** в Командная консоль Lync Server должно быть указано значение **True** .

4.  Сведения о настройке политики конференц-связи с помощью Командная консоль Lync Server см. в разделе [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy) документации по командной консоли Lync Server.

