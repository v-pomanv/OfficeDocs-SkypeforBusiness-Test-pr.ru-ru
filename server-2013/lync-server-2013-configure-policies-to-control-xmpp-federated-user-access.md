﻿---
title: "Lync Server 2013: настройка политик управл. доступом федер. XMPP-пользователей"
TOCTitle: Настройка политик управления доступом федеративных XMPP-пользователей
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ552446(v=OCS.15)
ms:contentKeyID: 49308962
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013

 

_**Дата изменения раздела:** 2012-11-01_

Это предварительная редакция документации и она может меняться. Пустые разделы добавлены в качестве заполнителей.

При настройке политик для поддержки федеративных партнеров XMPP (расширяемый протокол обмена сообщениями и контроля присутствия) политики применяют к пользователям федеративных доменов XMPP, а не к пользователям поставщиков (например, Windows Live) услуг обмена мгновенными сообщениями по протоколу SIP (Session Initiation Protocol) или федеративных доменов SIP. **Федеративного партнера XMPP** настраивают для каждого федеративного домена XMPP, в котором пользователям разрешается добавлять контакты и взаимодействовать с ними. Политики федеративных партнеров XMPP доступны только в одной области, хотя политика не определяется как глобальная, она действует как глобальная политика. Чтобы определить для федеративных партнеров XMPP глобальную политику, политику уровня сайта или пользователя, настраивают область действия политики путем создания и настройки политики внешнего доступа для требуемой области действия. Сведения о типах политик, которые можно настроить для внешнего доступа и федерации, см. в разделе [Управление федерацией и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по эксплуатации.

> [!NOTE]  
> Все политики <strong>федерации и внешнего доступа</strong> применяются через предоставление внутренних полос. Политики, которые применяются к пользователям, принадлежат сайту или являются глобальными по области действия, доводятся до клиента во время входа в систему. Политики для управления доступом федеративных партнеров XMPP можно настроить, даже если для вашей организации не включена XMPP-федерация. Однако настраиваемые политики вступают в действие, только когда для организации развернута, включена и настроена федерация партнеров XMPP. Сведения о развертывании и настройке федерации партнеров XMPP см. в разделе <a href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Настройка федерации SIP, федерации XMPP и общедоступных служб обмена мгновенными сообщениями в Lync Server 2013</a> в документации по развертыванию. Кроме того, если указать политику уровня пользователя в политике внешнего доступа для управления федеративными партнерами XMPP, эта политика применяется только к пользователям, которые разрешены для Lync Server 2013 и сконфигурированы для использования данной политики.

## Чтобы изменить глобальную политику для федеративных партнеров XMPP

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес для администрирования, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server см. в разделе [Открытие средств администрирования Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Внешний доступ пользователей** , затем щелкните **Политика внешнего доступа** .

4.  На странице **Политика внешнего доступа** выполните следующие действия в отношении глобальной политики:

5.  Выберите глобальную политику, щелкните **Изменить** , а затем щелкните "Подробнее".

6.  Предоставьте описание глобальной политики (по желанию).

7.  Выберите **Разрешить взаимодействие с федеративными пользователями** .

8.  Выберите **Разрешить связь с федеративными пользователями XMPP** .

9.  Щелкните **Зафиксировать** , чтобы сохранить изменения в глобальной политике.

## Чтобы создать политику уровня сайта или пользователя для федеративных партнеров XMPP

1.  Щелкните **Создать** , а затем щелкните **Политика уровня сайта** или **Политика уровня пользователя** . В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК** .

2.  Предоставьте описание политики сайта (по желанию).

3.  В политике уровня сайта или пользователя выберите настройку **Разрешить связь с федеративными пользователями** .

4.  Выберите **Разрешить связь с федеративными пользователями XMPP** .

5.  Нажмите кнопку **Commit** (Сохранить), чтобы сохранить изменения в политике на уровне сайта или пользователя.

## Чтобы изменить существующую политику для федеративных партнеров XMPP

1.  Чтобы изменить существующую политику, выберите соответствующую политику в списке, щелкните **Изменить** , а затем щелкните **Подробнее** .

2.  Измените или обновите описание политики (по желанию).

3.  Выберите или отмените выбор настройки **Разрешить связь с федеративными пользователями** .

4.  выберите или отмените выбор настройки **Разрешить связь с федеративными пользователями XMPP** .

5.  Щелкните **Зафиксировать** , чтобы сохранить изменения в политике.

## Изменение существующей политики для для федеративных партнеров XMPP с помощью Windows PowerShell

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Откройте Командная консоль Lync Server и введите следующее:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Пример команды, устанавливающей глобальную политику для разрешения доступа (значение «True») федеративных пользователей и разрешения доступа (значение «True») в XMPP-домен:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

## Создание политики уровня сайта или пользователя для федеративных партнеров XMPP с помощью Windows PowerShell

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Откройте Командная консоль Lync Server и введите следующее:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Пример команды, устанавливающей политику уровня сайта для сайта Редмонда с целью разрешить доступ федеративных пользователей и разрешить доступ в XMPP-домен:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

## Удаление существующей политики для федеративных партнеров XMPP с помощью Windows PowerShell

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Откройте Командная консоль Lync Server и введите следующее:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Пример команды, удаляющей политику уровня пользователя:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Пример команды, сбрасывающей глобальную политику в настройки по умолчанию:
    
        Remove-CsExternalAccessPolicy -Identity global

## См. также

#### Задачи

[Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  

#### Другие ресурсы

[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

