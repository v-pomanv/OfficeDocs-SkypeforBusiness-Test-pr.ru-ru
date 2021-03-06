﻿---
title: "Lync Server 2013: политика маршрутизации VoIP для пользователей филиалов"
TOCTitle: Создание политики маршрутизации VoIP для пользователей филиалов
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg398196(v=OCS.15)
ms:contentKeyID: 49308974
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание политики маршрутизации VoIP для пользователей филиалов в Lync Server 2013

 

_**Дата изменения раздела:** 2012-09-23_

Рекомендуется создавать отдельную политику VoIP для пользователей на сайтах филиалов. Эта политика должна содержать маршруты для выхода из шлюза устройства для обеспечения связи в филиалах или из внешнего шлюза сервера для обеспечения связи в филиалах и резервные маршруты для вызова из шлюза на центральном сайте. Независимо от того, где зарегистрирован пользователь, в регистраторе на устройстве для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах, или в резервном кластере регистратора на центральном сайте, политика VoIP пользователя всегда действительна.

## Настройка политики маршрутизации VoIP для пользователей филиалов

1.  Создайте абонентскую группу на уровне пользователя и назначьте ее пользователям филиалов. (См. раздел [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) документации по операциям.)

2.  Назначьте правила нормализации, соответствующие привычному для пользователей этого сайта набору номера. Если пользователь устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах при сбое перемещается в резервный пул регистратора на центральном сайте, то будет действовать все та же абонентская группа. (См. раздел [Создание абонентской группы в Lync Server 2013](lync-server-2013-create-a-dial-plan.md) документации по операциям.)

3.  Настройте маршрут голосовых вызовов, который выходит из шлюза устройства для обеспечения связи в филиалах или внешнего шлюза сервера для обеспечения связи в филиалах. (См. раздел [Создание голосового маршрута в Lync Server 2013](lync-server-2013-create-a-voice-route.md) документации по операциям.)

4.  Установите резервный маршрут вызовов в шлюзе устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах, указывающий на резервный пул регистратора (совместно размещенный с сервером-посредником) на центральном сайте. (См. документацию вашего поставщика устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах.)
    
    > [!NOTE]  
    > Настройка этого резервного маршрута вызовов помогает обеспечить работу входящих вызовов для пользователя филиала при недоступности устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах (например, при отключении на обслуживание). Если регистратор и сервер-посредник в устройстве для обеспечения связи в филиалах или на сервере для обеспечения связи в филиалах недоступны, и пользователь зарегистрирован в резервном пуле регистратора на центральном сайте, то входящие вызовы будут продолжать направляться этому пользователю.

**Дальнейшее действие**: [Настройка параметров повторной маршрутизации для голосовой почты в Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

