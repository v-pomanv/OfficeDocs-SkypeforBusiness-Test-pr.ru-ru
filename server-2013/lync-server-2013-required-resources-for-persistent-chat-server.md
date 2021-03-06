﻿---
title: 'Lync Server 2013: необходимые ресурсы для сервера сохраняемого чата'
TOCTitle: Необходимые ресурсы
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ205211(v=OCS.15)
ms:contentKeyID: 49311015
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Необходимые ресурсы для сервера сохраняемого чата в Lync Server 2013

 

_**Дата изменения раздела:** 2016-02-05_

Высокий уровень доступности и аварийное восстановление сохраняемого сеанса беседы требуют больше ресурсов, чем обычно требуется для полнофункциональной работы. Перед настройкой сохраняемого сеанса беседы для обеспечения высокого уровня доступности и аварийного восстановления убедитесь в наличии перечисленных ниже ресурсов в дополнение к ресурсам, требуемым для стандартных операций сохраняемого сеанса беседы. Дополнительные сведения о настройке см. в разделе [Настройка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Один выделенный экземпляр базы данных, расположенный в одном физическом центре обработки данных с сервером переднего плана службы сохраняемого сеанса беседы. Эта база данных будет выступать в роли зеркала SQL Server для базы данных-источника сохраняемый сеанс беседы. Кроме того, если вы хотите автоматизировать отработку отказа в зеркальной базе данных, назначьте дополнительный SQL Server в качестве следящего сервера зеркального отображения.

  - Один выделенный экземпляр базы данных, расположенный в другом физическом центре обработки данных. Эта база данных будет выступать в роли базы данных-получателя доставки журналов SQL Server для базы данных в основном центре обработки данных.

  - Один выделенный экземпляр базы данных, выступающий в роли зеркала SQL Server для базы данных-получателя. Можно дополнительно назначить SQL Server в качестве следящего сервера зеркального отображения. Обе базы данных должны быть расположены в одном физическом центре обработки данных в качестве базы данных-получателя.

  - Если обеспечение соответствия сохраняемого сеанса беседы включено, требуется 3 дополнительных выделенных экземпляра базы данных. Распространение этих экземпляров выполняется аналогично базе данных сохраняемый сеанс беседы, описанному выше. Хотя база данных соответствия может использовать один экземпляр SQL Server совместно с базой данных сохраняемый сеанс беседы, мы рекомендуем изолированные экземпляры для обеспечения высокого уровня доступности и аварийного восстановления.

  - Для журналов транзакций доставки журналов SQL Server необходимо создать и назначить файловый ресурс. Все серверы SQL Servers в обоих центрах управления данными, на которых выполняются базы данных сохраняемый сеанс беседы, должны иметь доступ на чтение/запись для этой общей папки. Этот файловый ресурс не задается как часть роли хранилища файлов.

  - Файловый ресурс на сервере базы данных-получателя в качестве конечной папки для журналов транзакций SQL Server, которые копируются с общего файлового ресурса сервера-источника.

На следующих рисунках показаны примеры настройки серверов сохраняемого сеанса беседы для двух разных топологий вытянутого пула:

  - Растянутый пул серверов сохраняемого сеанса беседы для территориально-распределенных центров обработки данных с высокой пропускной способностью и небольшой задержкой

  - Растянутый пул серверов сохраняемого сеанса беседы для территориально-распределенных центров обработки данных с низкой пропускной способностью и большой задержкой

На следующем рисунке показана топология растянутого пула серверов сохраняемого сеанса беседы для территориально-распределенных центров обработки данных с высокой пропускной способностью и небольшой задержкой.

**Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с высокой пропускной способностью и небольшой задержкой**

![Пример конфигурации HBW пула серверов сохраняемого чата](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Пример конфигурации HBW пула серверов сохраняемого чата")

На следующем рисунке показана топология растянутого серверов сохраняемого сеанса беседы для территориально-распределенных центров обработки данных с низкой пропускной способностью и большой задержкой.

**Растянутый пул серверов сохраняемого чата для территориально-распределенных центров обработки данных с низкой пропускной способностью и большой задержкой**

![Пример конфигурации LBW пула серверов сохраняемого чата](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Пример конфигурации LBW пула серверов сохраняемого чата")

