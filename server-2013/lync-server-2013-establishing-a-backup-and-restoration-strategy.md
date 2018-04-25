﻿---
title: Определение стратегии резервного копирования и восстановления
TOCTitle: Определение стратегии резервного копирования и восстановления
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh202195(v=OCS.15)
ms:contentKeyID: 52058548
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Определение стратегии резервного копирования и восстановления

 

_**Дата изменения раздела:** 2013-03-26_

Перед созданием плана резервного копирования и восстановления для Lync Server необходимо разработать стратегию, соответствующую целям организации. Чтобы получить эффективную стратегию резервного копирования и восстановления, необходимо выполнить следующее.

  - Установить бизнес-приоритеты.

  - Определить требования к резервному копированию и восстановлению.

## Установка приоритетных направлений деятельности

Оцените бизнес-приоритеты вашей организации. На стратегию резервного копирования и восстановления обычно влияют следующие основные бизнес-приоритеты:

  - требования к непрерывности ведения бизнеса;

  - полнота данных;

  - важность данных;

  - требования к переносимости;

  - ограничения затрат.

Деловые потребности, подобно указанным здесь, помогают определить соглашения об уровне обслуживания (SLA), которые вы разрабатываете со своими клиентами. Соглашения об уровне обслуживания серьезно влияют на стратегию резервного копирования и восстановления.

## Определение требований к резервному копированию и восстановлению

Ваши бизнес-приоритеты и соглашения об уровне обслуживания действуют при определении требований организации к резервному копированию и восстановлению Lync Server. Определите и задокументируйте требования для следующих аспектов.

  - **Частота резервного копирования.**   Следует учитывать, что за исключением интерфейсных пулов в отношениях связывания, которые описываются в статье [Планирование высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md), Lync Server поддерживает только простую модель восстановления, в которой восстановление выполняется до последней полной резервной копии. Тщательно планируйте частоту полного резервного копирования. Рекомендации по частоте резервного копирования см. в статье [Рекомендации по резервному копированию и восстановлению](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Средства резервного копирования и восстановления.**   Определите, кто будет использовать эти средства и на каких компьютерах. Сведения о средствах, рассматриваемых в данной статье, и о необходимых разрешениях см. в статье [Требования к резервному копированию и восстановлению: средства и разрешения](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Расположение резервных копий.**   Определите, как должны сохраняться резервные копии, локально или удаленно, учитывая безопасность и доступность. Укажите носители, которые будут использоваться для резервных копий.

  - **Требования к оборудованию и программному обеспечению.**   Определите и задокументируйте ваши особые требования к оборудованию и программному обеспечению, включая оборудование для хранилища резервных копий и восстановления определенных компонентов, а также все программное обеспечение и сетевые подключения, которые необходимы для поддержки резервного копирования и восстановления. При разработке требований к оборудованию и программному обеспечению учитывайте разные сценарии восстановления, которые рассматриваются ниже.

  - **Сценарии восстановления.**   Далее приводятся процессы восстановления для нескольких сценариев.
    
      - Сбой пула Lync Server. В этом сценарии требуется перестроить каждый сервер в пуле.
    
      - Сбой сервера Сервер Standard Edition. В этом сценарии требуется перестроить сервер на новом или очищенном компьютере и восстановить базы данных.
    
      - Потеря центрального хранилища управления. В этом сценарии требуется как минимум восстановить и опубликовать центральное хранилище управления.
    
      - Потеря тылового сервера при нормальном функционировании центрального хранилища управления. В этом сценарии требуется перестроить сервер на новом или очищенном компьютере и восстановить базы данных.
    
      - Сбой сервера, являющегося членом пула Lync Server. В этом сценарии требуется перестроить сервер на новом или очищенном компьютере и восстановить базы данных.
    
      - Сбой хранилища файлов. В этом сценарии требуется восстановить файловый сервер или файловый кластер.
    
      - Сбой базы данных архивации, мониторинга или сохраняемого чата. В этом сценарии требуется пересоздать базы данных и в случае, если данные критически важны для организации, восстановить их. Данные архивации, мониторинга и сохраняемого чата не требуются для получения резервной копии Lync Server и его работы.
