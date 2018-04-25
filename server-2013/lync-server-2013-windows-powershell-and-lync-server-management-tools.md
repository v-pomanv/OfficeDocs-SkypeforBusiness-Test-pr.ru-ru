﻿---
title: 'Lync Server 2013: средства управления для Windows PowerShell и Lync Server 2013'
TOCTitle: Средства управления для Windows PowerShell и Lync Server 2013
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59679353
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Средства управления для Windows PowerShell и Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

На сервере Microsoft Lync Server 2013 средства управления реализованы с помощью Windows PowerShell. Windows PowerShell предоставляет среду командной строки, команды для определенных продуктов и полноценный язык сценариев. Средства Lync Server 2013 реализованы с помощью Windows PowerShell, включая указанные ниже элементы.

  - **топологий**. Средство топологий используется для создания, корректировки и публикации запланированной топологии, а также проверяет топологию перед началом установки серверов. При установке сервера Lync Server 2013 на отдельные серверы считываются данные о созданном развертывании и программа установки развертывает сервер в соответствии с инструкциями, заданными в топологии. После настройки сведения о конфигурации автоматически реплицируются на все серверы. Компоненты можно добавить в развертывание только при использовании построителя топологий.

  - **Командная консоль Lync Server**. Командная консоль Lync Server используется для полноценного управления развертыванием с помощью командной строки.

  - **управления Lync Server**. Интерфейс пользователя управления Microsoft Lync Server 2013 используется для управления самыми обычными задачами в развертывании.

В этих средствах используются командлеты Windows PowerShell для управления развертыванием, включая почти 550 командлетов для различных продуктов. Командлеты обеспечения безопасности, включенные в Lync Server 2013, в основном используются для управления проверкой подлинности, а также пользовательскими правами и привилегиями. Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов). Кроме того, существует множество командлетов, позволяющих использовать новую функцию управления доступом на основе ролей (RBAC) для делегирования прав администрирования Lync Server 2013. Подробные сведения о командлетах Lync Server см. в разделе [Командная консоль Lync Server](lync-server-2013-lync-server-management-shell.md) документации по эксплуатации. Подробные сведения по использованию топологий и управления Lync Server 2013 для управления развертыванием см. в разделе [Панель управления Lync Server 2013](https://technet.microsoft.com/ru-ru/library/gg133224\(v=ocs.15\)) документации по эксплуатации.

Функции безопасности сценария для Windows PowerShell специально разработаны для помощи в предотвращении некоторых связанных с написанием сценария проблем безопасности старых топологий, включая сценарии VBScript. Функции безопасности Windows PowerShell предназначены для создания среды, в которой пользователи не смогут случайно или без усилий запускать сценарии. По умолчанию функции безопасности Windows PowerShell включены. Состояние этих функций можно изменять в соответствии с требованиями написания сценариев и различными целями безопасности. Это не означает, что оболочка делает запуск сценариев для пользователей невозможным. Наоборот, оболочка по умолчанию затрудняет для пользователей запуск сценариев без понимания того, что они делают. Подробные сведения см. в разделе безопасности сценариев Windows PowerShell по адресу [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).
