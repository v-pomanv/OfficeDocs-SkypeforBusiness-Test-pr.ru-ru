﻿---
title: 'Lync Server 2013: поддержка групповых сертификатов'
TOCTitle: Поддержка групповых сертификатов
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Hh202161(v=OCS.15)
ms:contentKeyID: 49308909
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Поддержка групповых сертификатов в Lync Server 2013

 

_**Дата изменения раздела:** 2013-03-21_

Система Lync Server 2013 использует сертификаты для обеспечения шифрования передаваемых данных и проверки подлинности удостоверения сервера. В некоторых ситуациях, таких как веб-публикация через обратный прокси-сервер, строгое соответствие записи альтернативного имени субъекта с полным доменным именем сервера, представляющего службу, не требуется. В этом случае вы можете использовать сертификаты с записями альтернативного имени субъекта с подстановочными знаками (более известные как «групповые сертификаты»), чтобы сократить стоимость сертификата, запрашиваемого из общего центра сертификации и снизить сложность процесса планирования для сертификатов.

> [!WARNING]  
> Чтобы сохранить функциональные возможности устройств объединенных коммуникаций (например, стационарного телефона), вам следует тщательно протестировать развернутый сертификат и убедиться, что после применения группового сертификата все устройства работаю правильно.

Ни для одной из ролей нет поддержки записи с подстановочными знаками в качестве имени субъекта (которое также называется общим именем). При использовании записей с подстановочными знаками в альтернативном имени субъекта поддерживаются следующие роли сервера:

   **Обратный прокси-сервер.**   Запись альтернативного имени субъекта с подстановочными знаками поддерживается для сертификата публикации с простым URL-адресом (meet и dialin).

   **Обратный прокси-сервер.**   Запись альтернативного имени субъекта с подстановочными знаками поддерживается для записей альтернативного имени субъекта для LyncDiscover в сертификате публикации.

   **Director.**Запись альтернативного имени субъекта с подстановочными знаками поддерживается для простых URL-адресов (meet и dialin) и записей альтернативного имени субъекта для LyncDiscover и LyncDiscoverInternal в веб-компонентах сервера Director.

   **переднего плана ( Standard Edition) и переднего плана ( Enterprise Edition).** Запись альтернативного имени субъекта с подстановочными знаками поддерживается для простых URL-адресов (meet и dialin) и записей альтернативного имени субъекта для LyncDiscover и LyncDiscoverInternal в веб-компонентах сервера Director.

   **обмена сообщениями Exchange.**   Сервер не использует записи альтернативного имени субъекта при развертывании в качестве изолированного сервера.

   Сервер клиентского доступа **Microsoft Exchange Server.**   Записи с подстановочными знаками в альтернативном имени субъекта поддерживаются для внутренних и внешних клиентов.

   Единая система **обмена сообщениями Exchange и сервер клиентского доступа Microsoft Exchange Server на одном сервере.**   Записи альтернативного имени субъекта с подстановочными знаками поддерживаются.

Роли сервера, которые не рассматриваются в данном разделе:

  - Внутренние роли сервера (включая, среди прочего, сервер- посредник, сервер архивации и мониторинга, устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах)

  - Интерфейсы внешнего пограничного сервера

  - Внутренний пограничный сервер
    
    > [!NOTE]  
    > Для интерфейса внутреннего пограничного сервера запись с подстановочными знаками поддерживается и может быть назначена альтернативному имени субъекта. Альтернативное имя субъекта на внутреннем пограничном сервере не требуется, а запись альтернативного имени субъекта с подстановочными знаками имеет ограниченное применение.

Дополнительные сведения о конфигурациях сертификатов, включая использование подстановочных знаков в сертификатах, см. в следующих разделах:

  - [Требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Требования к сертификатам для доступа внешних пользователей в Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Сводка по сертификатам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Сводка по сертификатам — единственный директор в Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Сводка по сертификатам — масштабированный пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Сводка по сертификатам — обратный прокси-сервер в Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Дополнительные сведения о настройке сертификатов для Exchange, включая использование подстановочных знаков, см. в документации по продукту Exchange 2013.

