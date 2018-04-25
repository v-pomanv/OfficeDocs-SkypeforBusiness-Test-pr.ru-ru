﻿---
title: 'Lync Server 2013: запуск служб на серверах'
TOCTitle: Запуск служб на серверах
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg413059(v=OCS.15)
ms:contentKeyID: 49311725
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Запуск служб на серверах для Lync Server 2013

 

_**Дата изменения раздела:** 2014-09-03_

Для успешного выполнения этой процедуры необходимо войти в систему с учетной записью, которая входит в группу RTCUniversalServerAdmins или имеет соответствующие разрешения. Дополнительные сведения о делегировании разрешений см. в статье [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

После установки локального хранилища конфигурации на серверах установите компоненты Lync Server 2013 и настройте сертификаты на сервере переднего плана или переднего плана. Кроме того, на сервере необходимо запустить службы Lync Server 2013. Ниже приведена процедура запуска служб на каждом сервере переднего плана в развертывании.

## Запуск служб на сервере переднего плана или в стандартном выпуске сервера

1.  В средстве развертывания Lync Server на странице **Lync Server 2013** нажмите кнопку **Выполнить** для шага **Step 4: Start Services** (Шаг 4. Запуск служб).

2.  На странице **Запуск служб** нажмите **Далее**, чтобы запустить службы Lync Server на сервере.

3.  После того как все службы будут успешно запущены, на странице **Выполнение команд** нажмите кнопку **Готово** .
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ618369.important(OCS.15).gif" title="important" alt="important" />Важно!</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Использование команды для запуска служб на сервере – это лучший способ, позволяющий получить подтверждение того, что службы действительно запущены. Однако он может не отражать фактическое состояние служб. Рекомендуется использовать шаг <strong>Service Status (Optional)</strong> (Состояние службы (дополнительно)) сразу после шага <strong>Запуск служб</strong> , чтобы открыть консоль управления (MMC) и убедиться в том, что все службы успешно запущены. Если какая-либо из служб Lync Server не запущена, можно щелкнуть ее правой кнопкой мыши в консоли MMC и выбрать команду <strong>Запуск</strong> .</td>
    </tr>
    </tbody>
    </table>
