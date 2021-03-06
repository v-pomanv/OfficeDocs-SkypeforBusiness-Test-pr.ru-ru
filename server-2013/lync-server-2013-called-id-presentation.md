﻿---
title: Презентация идентификатора звонящего в Lync Server 2013
TOCTitle: Презентация идентификатора звонящего в Lync Server 2013
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49888199
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Презентация идентификатора звонящего в Lync Server 2013

 

_**Дата изменения раздела:** 2016-12-08_

Lync Server 2010 позволяет преобразовывать номер телефона вызываемой стороны (то есть номер телефона, на который осуществляется вызов) из формата E.164 в формат местного набора в соответствии с требованиями *магистрального узла* (то есть связанного шлюза, магистрали PBX или SIP). Для этого необходимо определить одно или несколько правил преобразования для преобразования URI запроса перед переадресованием на магистральный узел.

> [!IMPORTANT]  
> Возможность связывания одного или нескольких правил преобразования с магистральной конфигурацией корпоративной голосовой связи используется в качестве <em>альтернативы</em> процесса настройки правил преобразования на магистральном узле. Не связывайте правила преобразования с магистральной конфигурацией корпоративной голосовой связи, если вы настроили правила преобразования на магистральном узле, так как возможен конфликт этих двух правил.

Вы можете использовать один из следующих методов для создания или изменения правила преобразования:

  - Используйте средство **создания правила преобразования**, чтобы указать значения для начальных символов, длины, отсекаемых и добавляемых символов, а затем средство управления Lync Server создает соответствующий шаблон сопоставления и правило преобразования.

  - Запишите регулярные выражения вручную, чтобы определить шаблон сопоставления и правило преобразования.

> [!NOTE]  
> Информацию о записи регулярных выражений см. в разделе «Регулярные выражения .NET Framework» на веб-сайте <a href="http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x419" class="uri">http://go.microsoft.com/fwlink/?linkid=140927&amp;clcid=0x419</a>.

## Содержание

  - [Создание или изменение правила преобразования с помощью средства построения правила преобразования](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Создание или изменение правила преобразования вручную](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

## См. также

#### Концепции

[Отображение идентификатора звонящего в Lync Server 2013](lync-server-2013-caller-id-presentation.md)

