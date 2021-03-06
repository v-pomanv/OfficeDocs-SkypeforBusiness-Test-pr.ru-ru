﻿---
title: Удаление рабочего процесса
TOCTitle: Удаление рабочего процесса
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg520944(v=OCS.15)
ms:contentKeyID: 49308797
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Удаление рабочего процесса

 

_**Дата изменения раздела:** 2012-11-01_

Для удаления рабочего процесса воспользуйтесь одной из следующих процедур.

## Использование панели управления Lync Server для удаления рабочего процесса

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Группы ответа**, а затем щелкните **Рабочий процесс**.

4.  На странице **Рабочий процесс** нажмите кнопку **Создать или изменить рабочий процесс**.

5.  В поле поиска **Выбрать услугу** введите часть имени или полное имя службы **ApplicationServer**, где размещается рабочий процесс, который нужно удалить.

6.  В списке служб выберите нужную службу, а затем нажмите кнопку **ОК**.
    
    > [!NOTE]  
    > Откроется веб-страница настройки группы ответа. Вы также можете открыть веб-страницу настройки группы ответа напрямую из браузера, подключившись к <strong>https://<em>&lt;полное_доменное_имя_пула&gt;</em>/RgsConfig</strong>.

7.  В окне **Управление существующим рабочим процессом** найдите рабочий процесс, который нужно удалить, а затем в разделе **Действие** нажмите кнопку **Удалить**.

8.  Нажмите кнопку **Да**.

## Использование командлетов для удаления рабочего процесса

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните в командной строке следующую команду:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Пример:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

