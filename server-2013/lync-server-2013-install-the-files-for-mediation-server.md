﻿---
title: 'Lync Server 2013: установка файлов для сервера-посредника'
TOCTitle: Установка файлов для сервера-посредника
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Gg412998(v=OCS.15)
ms:contentKeyID: 49311617
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Установка файлов для сервера-посредника в Lync Server 2013

 

_**Дата изменения раздела:** 2012-08-06_

Для успешного выполнения этой процедуры необходимо войти на сервер как минимум с учетной записью локального администратора и пользователя домена, которая является членом группы RTCUniversalReadOnlyAdmins или группы, имеющей более высокие привилегии.

Выполните действия, описанные в этом разделе, для запуска мастера развертывания Lync Server 2013 и установки файлов для посредник на компьютере, добавленном в серверов-посредников при использовании построителя топологии для определения и публикации пула. При установке файлов посредник вы также устанавливаете и назначаете сертификат, необходимый каждому компьютеру в серверов-посредников.

На этом сайте, если вы уже развернули Серверы-посредники с совместным размещением в переднего плана или Сервер Standard Edition, вы можете пропустить этот раздел и перейти к разделу [Конфигурация магистралей в Lync Server 2013](lync-server-2013-configuring-trunks.md).

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398412.note(OCS.15).gif" title="note" alt="note" />Примечание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>В данном разделе предполагается, что вы уже определили и опубликовали автономный пул серверов-посредников, как описано в статьях <a href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Определение сервера-посредника в построителе топологий в Lync Server 2013</a> и <a href="lync-server-2013-publish-the-topology.md">Публикация топологии в Lync Server 2013</a> в документации по развертыванию, и убедились, что компьютеры в серверов-посредников соответствуют требованиям, описанным в статьях <a href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Необходимое программное обеспечение для корпоративной голосовой связи в Lync Server 2013</a> и <a href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Необходимые условия для обеспечения безопасности и настройки корпоративной голосовой связи в Lync Server 2013</a>.</td>
</tr>
</tbody>
</table>


## Установка файлов для автономного пула серверов-посредников

1.  На установочном носителе щелкните правой кнопкой файл *\<установочный\_носитель\>* **\\Setup\\amd64\\Setup.exe** и выберите команду **Запуск от лица администратора**.

2.  На странице **Папка установки** нажмите **ОК**.

3.  На странице **Лицензионное соглашение** нажмите кнопку **Принимаю**, а затем нажмите **ОК**. (Требуется для продолжения.)

4.  На странице **мастера развертывания Lync Server 2010** щелкните **Установить или обновить Lync Server**.

5.  Рядом со строкой **Шаг 1. Установка локального хранилища конфигурации** нажмите кнопку **Выполнить** и следуйте инструкциям на экране.

6.  На странице **Настройка локальной реплики центрального хранилища управления** примите значение параметра **Извлечь данные непосредственно из центрального хранилища управления** по умолчанию и нажмите кнопку **Далее**.

7.  На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.

8.  Рядом со строкой **Шаг 2. Установка и удаление компонентов Lync Server** нажмите кнопку **Выполнить**, а затем нажмите **Далее**.

9.  На странице **Выполнение команд**, когда состояние задачи отображается как **Завершено**, нажмите кнопку **Готово**.

10. Нажмите кнопку **Выполнить** рядом со строкой **Шаг 3. Запрос, установка и назначение сертификатов**. Следуйте инструкциям на экране, приняв значения по умолчанию. Для сервера-посредника требуется один сертификат, поэтому вы выполните **Шаг 3** дважды: один раз, чтобы издать нужный сертификат, и второй раз, чтобы его назначить.

11. После выдачи и корректного назначения сертификата нажмите рядом со строкой **Шаг 4. Запуск служб** кнопку **Выполнить** и следуйте инструкциям на экране.

12. После успешного завершения **шага 4** перезапустите сервер и войдите на него как участник группы DomainAdmins.

13. На компьютере, где запущена панель управления Lync Server, убедитесь на странице **Топология** панели управления Lync Server, что состояние службы сервера-посредника отображается как зеленая галочка. Если вместо нее показан красный символ X, выберите сервер-посредник. В меню **Действие** щелкните **Запустить все службы**.

Если вы добавили несколько компьютеров в пул серверов-посредников, выполните действия, описанные здесь, на всех других компьютерах в серверов-посредников. Если вам не требуется устанавливать файлы для посредник на других компьютерах, выполните действия, описанные в разделе [Конфигурация магистралей в Lync Server 2013](lync-server-2013-configuring-trunks.md), чтобы настроить параметры магистрального подключения между этим пулом серверов-посредников (или всеми серверами-посредниками на сайте) и его одноранговым узлом.

## См. также

#### Концепции

[Требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)
