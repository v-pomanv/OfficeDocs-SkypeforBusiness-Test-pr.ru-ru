﻿---
title: "Lync Server 2013: восстан. содержимого конференций с пом. службы архивации"
TOCTitle: Восстановление содержимого конференций с помощью службы резервного копирования
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49887957
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

Если сведения о конференциях, содержащиеся в хранилище файлов на интерфейсном пуле, становятся недоступными, необходимо восстановить эти сведения, чтобы пользователи, размещенные в пуле, сохранили свои данные конференций. Если интерфейсный пул, утративший данные конференций, объединен в пару с другим интерфейсным пулом, можно использовать службу резервного копирования для восстановления данных.

Необходимо также выполнить эту задачу, если вследствие сбоя не работает весь пул и необходимо перенести его пользователей в резервный пул. При восстановлении пользователей в исходном пуле необходимо использовать эту процедуру для копирования контента конференций обратно в исходный пул.

Предположим, что пул1 объединен с пулом2, а данные конференций в пуле1 утрачены. Можно использовать приведенный ниже командлет для вызова службы резервного копирования в целях восстановления содержимого.

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Восстановление содержимого конференций может занять некоторое время в зависимости от размера. Можно использовать приведенный ниже командлет для проверки состояния процесса:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Процесс завершается, когда этот командлет возвращает значение Steady State для данных в модуле конференций.

