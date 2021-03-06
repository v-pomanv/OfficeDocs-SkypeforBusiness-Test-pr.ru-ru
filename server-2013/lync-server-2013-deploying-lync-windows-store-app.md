﻿---
title: Развертывание приложения Lync из Магазина Windows
TOCTitle: Развертывание приложения Lync из Магазина Windows
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/JJ822971(v=OCS.15)
ms:contentKeyID: 52058283
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Развертывание приложения Lync из Магазина Windows

 

_**Дата изменения раздела:** 2016-12-08_

Перед тем как делать Магазина Lync Windows доступным пользователям, убедитесь в том, что ваша система соответствует требованиям, описанным в разделе [Требования приложения Lync из Магазина Windows](lync-server-2013-lync-windows-store-app-requirements.md). Подробные сведения о настройке поддержки Магазина Lync Windows в Lync Server 2013 см. в статье блога NextHop "Автообнаружение Lync Server и приложение Lync в Магазине Windows" по адресу [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966). Правильно настроив серверную среду, вы можете дать пользователям указание загрузить приложение Lync из Магазина Windows, выполнив поиск по запросу "Lync".

## Включение многофакторной проверки подлинности для Магазина Lync Windows

В Накопительные пакеты обновления для Lync Server 2013: июнь 2013 г. добавлена поддержка многофакторной проверки подлинности для клиентов Магазина Lync Windows. Для проверки подлинности внешних пользователей, подключающихся к собраниям Lync, можно настроить обязательное использование не только имени пользователя и пароля, но и дополнительных средств, таких как смарт-карты и ПИН-коды. Чтобы включить многофакторную проверку подлинности, необходимо развернуть сервер служб федерации Active Directory и включить пассивную проверку подлинности в Lync Server 2013. После настройки служб федерации Active Directory внешние пользователи, пытающиеся присоединиться к собраниям Lync, перенаправляются на веб-страницу многофакторной проверки подлинности, на которой они должны ввести имя пользователя и пароль, а также использовать дополнительные способы для собственной идентификации.

> [!IMPORTANT]  
> Если вы планируете настроить службы федерации Active Directory с целью обеспечения многофакторной проверки подлинности для Магазина Lync Windows, учтите следующие рекомендации.
> <ul><li><p>Требуется как минимум Lync Server 2013 с Накопительные пакеты обновления для Lync Server 2013: июнь 2013 г.. Клиентам Lync 2013 для настольных систем не требуется Накопительные пакеты обновления для Lync Server 2013: июнь 2013 г., поэтому может казаться, что пассивная проверка подлинности работает, так как клиенты Lync 2013 могут пройти проверку подлинности. Однако процесс проверки подлинности для клиентов Магазина Lync Windows будет завершаться сбоем. При этом уведомления и сообщения об ошибках не выводятся.</p></li>
> <li><p>Необходимо настроить сервер так, чтобы пассивная проверка подлинности была единственным предлагаемым типом проверки подлинности.</p></li>
> <li><p>Если вы используете аппаратные балансировщики нагрузки, включите на них сохранение файлов cookie, чтобы все запросы от клиента Магазина Lync Windows обрабатывались одним сервером переднего плана.</p></li>
> <li><p>Если вы устанавливаете отношение доверия с проверяющей стороной между Lync Server и серверами служб федерации Active Directory, задайте срок действия маркера не менее максимальной продолжительности собраний Lync. Как правило, 240 минут бывает достаточно.</p></li></ul>

**Настройка многофакторной проверки подлинности**

1.  Установите роль сервера федерации служб федерации Active Directory. Подробные сведения см. в руководстве по развертыванию служб федерации Active Directory 2.0 по адресу <http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Создайте сертификаты для служб федерации Active Directory. Дополнительные сведения см. в разделе "Сертификаты сервера федерации" статьи "Планирование и развертывание служб федерации Active Directory для использования с единым входом" на странице [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Введите в командной строке Windows PowerShell следующую команду:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Установите партнерство, выполнив следующую команду:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Настройте следующие правила проверяющей стороны:
    
```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
```
```    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
    
```
```
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
```

## Известные проблемы со входом

## Время и дата на устройстве, на котором работает Магазина Lync Windows, установлены неправильно

Время на устройстве должно быть синхронизировано со временем на сервере. Это особенно важно для таких устройств, как Microsoft Surface, и других устройств с ОС Windows RT, которые не присоединены к домену. Чтобы автоматически синхронизировать время на этих устройствах с сервером времени, в командной строке с повышенными привилегиями на устройстве выполните следующую команду:

    w32tm /resync

## Магазина Lync Windows не может получить доступ к серверу или службам Lync

В Магазина Lync Windows может отсутствовать доступ к серверу или службам Lync через сетевые адаптеры, например USB-модемы 4G LTE, которые не регистрируются в Windows 8 как физические устройства. Эта проблема может возникать в Магазина Lync Windows даже в том случае, если приложения для настольных систем и браузеры имеют доступ к другим серверам и веб-сайтам.

## Приложение Lync из Магазина Windows не может выполнить вход в Lync Server 2010 и на пограничный сервер Office Communications Server 2007 R2

Если ваша топология состоит из Lync Server 2010 с пограничным сервером Office Communications Server 2007 R2, потребуется запустить обновленную версию построителя топологий, доступную в накопительном пакете обновления для Lync Server 2010 за июль 2013 г. Более ранние версии построителя топологий не создают необходимое сопоставление с пограничным сервером Office Communications Server 2007, поэтому клиентам приложения Lync из Магазина Windows не удается выполнить вход. Выполните указанные ниже действия.

1.  Установите накопительный пакет обновления для Lync Server 2010 за июль 2013 г. в пулах Lync Server 2010 и на директорах Lync Server 2010.

2.  Измените конфигурацию автообнаружения Lync, указав в качестве внешней точки входа SIP адрес пограничного сервера. Для этого выполните указанные ниже действия.
    
    1.  Откройте Командная консоль Lync Server.
    
    2.  Выполните следующую команду:
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

## Приложение Lync Магазина Windows не может выполнить вход из-за ошибки проверки имени сертификата.

Неполадки со входом могут происходить для пользователей Office 365, которые не используют последнюю версию Магазина Lync Windows. Обычно это происходит в случае нескольких доменов (например, при использовании кода URI для SIP **userA@domainZ.com** со значением пограничного сервера **sip.domainX.com**). Для устранения неполадки пользователи должны установить последнюю версию Магазина Lync Windows, для которой также требуется ОС Windows 8.1.

## Устранение неполадок с использованием журналов Магазина Lync Windows

Для устранения неполадок можно использовать журналы, создаваемые на устройстве. Они хранятся в следующей папке:

%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing

Перед получением журнала от пользователя убедитесь в том, что ведение журнала включено, а затем попросите пользователя сохранить журналы, чтобы вся информация из оперативной памяти также сохранилась в файлы на жестком диске.

**Включение ведения журнала**

1.  Откройте Магазина Lync Windows на устройстве.

2.  Проведите пальцем от правого края экрана. Если вы пользуетесь мышью, наведите указатель на правый верхний угол экрана, а затем переместите его вниз.

3.  Последовательно выберите пункты **Настройки**, **Параметры**, а затем задайте для параметра **Журналы диагностики** значение **Вкл**.

4.  Если параметр **Журналы диагностики** ранее был выключен, необходимо перезапустить приложение Lync. Для этого выполните одно из указанных ниже действий.
    
      - Перезапустите устройство.
    
      - Завершите задачу Lync и запустите приложение снова. Чтобы завершить задачу, откройте диспетчер задач Windows, выберите задачу **Lync** и щелкните пункт **Снять задачу**. Если задача Lync отсутствует в списке, выберите пункт **Подробнее** и просмотрите список **Фоновые процессы**.

**Сохранение журналов**

1.  Откройте Магазина Lync Windows на устройстве.

2.  Попытайтесь выполнить вход.

3.  Проведите пальцем от правого края экрана. Если вы пользуетесь мышью, наведите указатель на правый верхний угол экрана, а затем переместите его вниз.

4.  Последовательно выберите пункты **Настройки**, **О программе**, а затем выберите команду **Сохранить журналы**.

