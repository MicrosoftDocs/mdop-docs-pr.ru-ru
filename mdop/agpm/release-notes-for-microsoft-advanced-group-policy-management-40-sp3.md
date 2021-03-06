---
title: Заметки о выпуске для средства расширенного управления групповыми политиками Майкрософт4.0 с пакетом обновления3 (SP3)
description: Заметки о выпуске для средства расширенного управления групповыми политиками Майкрософт4.0 с пакетом обновления3 (SP3)
author: dansimp
ms.assetid: 955d7674-a8d9-4fc5-b18a-5a1639e38014
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 6e0da04d67b3d29135071e0bc82b8e01789e4e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818522"
---
# Заметки о выпуске для средства расширенного управления групповыми политиками Майкрософт4.0 с пакетом обновления3 (SP3)


Чтобы найти заметки о выпуске, нажмите клавиши CTRL + F.

Внимательно прочитайте эти заметки о выпуске, прежде чем устанавливать службу расширенного управления групповыми политиками (Pack3) 4.0 Service Management (SP3). Эти заметки о выпуске содержат сведения, необходимые для успешной установки РАСШИРЕНного доступа к данным с пакетом обновления (SP3) и содержащие сведения, недоступные в документации по продукту. Если существует разница между этими заметками о выпуске и другой документацией по РАСШИРЕНным анализом, рассматривайте Последнее изменение в полномочном виде. Эти заметки о выпуске заменяют контент, включенный в этот продукт.

## Известные проблемы с РАСШИРЕНным управлением ПАКЕТами


В этом разделе описаны известные проблемы, возникающие при работе с РАСШИРЕНным поиском, 4,0 SP3.

### Не удается установить РАСШИРЕНную версию Office в Windows 10

Функция "РАСШИРЕНная функциональность" обеспечивает возможность активации Windows Communication Foundation (WCF), не поддерживающей HTTP, во время установки. В Windows 10 в WCF включены требования для перезапуска Windows после включения функции активации WCF по протоколу HTTP. Однако текущий код установщика расширенного управления групповыми аналитиками не обрабатывает эти требования и перестает отвечать на запросы, пока служба не будет активирована.

**Временное решение:** Перед запуском установщика РАСШИРЕНного ключа установите флажок WCF не для активации HTTP, а затем перезапустите Windows.

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a>При попытке изменить параметры сервера расширенного управления групповыми политиками не работает средство удаления "Удалить"

Средство на панели управления, используемое для удаления или изменения программы, может не работать при попытке изменить параметры сервера расширенного управления групповыми политиками.

**Временное решение:** Перед изменением параметров сервера с помощью панели управления создайте копию папки архива с РАСШИРЕНным доступом к каталогу. Затем вы можете использовать Setup.exe для переустановки сервера РАСШИРЕНного использования службы и выбора нужных параметров конфигурации.

### В отчетах не отображаются ссылки, добавленные в объект групповой политики.

В отчетах "Параметры РАСШИРЕНного ключа" и "разница" не отображаются ссылки, добавленные в объект групповой политики (GPO).

**Временное решение:** Чтобы просмотреть ссылки в отчетах, выберите GPO в консоли управления групповыми политиками, а затем откройте вкладку **Параметры** в области справа.

### В отчетах не отображаются все параметры свойств параметров выбора

В отчетах "Параметры РАСШИРЕНного ключа" и "разница" отображаются не все параметры, выбранные в окне **свойств параметров выбора** в редакторе объектов групповой политики.

**Временное решение:** Используйте GPMC для просмотра выбранных параметров **свойств выбора** в отчетах.

### В некоторых браузерах в отчетах не отображаются вкладки "Показать" и "скрыть"

Вкладки **Показать** и **Скрыть** в правой части параметров расширенного аналитического отчета и в отчете о различиях могут не отображаться при просмотре отчетов в Google Chrome или Mozilla Firefox.

**Временное решение:** Просмотр отчетов с помощью браузера Internet Explorer.

### Параметры расширенного управления групповыми политиками и отчеты о различиях могут показывать различные данные из отчетов GPMC

В отчетах "Параметры РАСШИРЕНного управления и разница" могут отображаться не те же данные, что и отчеты в GPMC.

**Временное решение:** Используйте GPMC для просмотра отчетов расширенного управления групповыми политиками.

### Служба расширенного управления групповыми политиками не запускается, если контроллер домена не в сети

Если служба расширенного управления групповыми политиками установлена на контроллере домена в операционной системе Windows® 8 или более поздней версии операционной системы, служба не запускается, если контроллер домена не в сети.

**Временное решение:** Запустите службу расширенного управления групповыми политиками вручную после того, как контроллер домена в сети.

### При переходе с выпуска РАСШИРЕНного набора данных версии 4.0 и Hotfix1 будет заблокировано обновление сервера с расширенным управлением разгрузкой для РАСШИРЕНного обновления

Если вы попытаетесь обновить сервер РАСШИРЕНного обновления до РАСШИРЕНного уровня для 4,0. Пакет обновления 2 (SP2) после установки многоязыкового сервера РАСШИРЕНной версии 4,0, а затем Установка исправления для расширенного ключа с именем с помощью 4,0 РАСШИРЕНного проверки появления неверных различий в отчете HTML (см. статью базы знаний, статья [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), обновить

**Временное решение:** Удалите сервер РАСШИРЕНной версии 4,0, а затем установите пакет обновления 2 (SP2) для 4,0.

### В отчетах не отображаются ссылки на подразделение

Если вы привязать недоступный объект групповой политики к организационному подразделению, а затем управлять этим объектом групповой политики с помощью расширенного управления групповыми политиками, в отчетах "Параметры и разница" не отображаются ссылки на подразделение.

**Временное решение:** На вкладке **Управление** узлом **изменить параметры** щелкните объект групповой политики правой кнопкой мыши, выберите пункт **Параметры**, а затем — **ссылки GPO** для просмотра ссылок Организации. Кроме того, вы можете использовать GPMC для просмотра ссылок на объект групповой политики на вкладке **область** .

### При нажатии кнопки "назад" в диалоговом окне "изменение", "восстановление" или "удаление клиента с расширенным управлением групповыми политиками" отображается ошибка

Если вы открываете компонент " **программы и компоненты** " на панели управления, а затем выбираете пункт " **Дополнительные параметры групповой политики Майкрософт" — клиент**, функция расширенного управления версиями выводит сообщение об ошибке, если нажать кнопку **изменить** , а затем нажать кнопку **назад** в диалоговом окне **изменение, восстановление или удаление клиента с расширенным** доступом

**Временное решение:** Нажмите кнопку **Отмена** , чтобы очистить сообщение об ошибке, а затем запустите процесс еще раз. Не нажимайте кнопку " **назад** " после нажатия кнопки " **изменить** ".

### В окне журнала не отображается Примечание, когда утверждающий развертывает объект групповой политики и вводит Примечание.

Если пользователь, у которого есть роль редактора, отправляет запрос на развертывание объекта групповой политики, а пользователь, который имеет роль утверждающего, разворачивает объект GPO и вводит Примечание, этот комментарий не отображается в окне **журнала** .

**Временное решение:** Ничего.

### Добавлен механизм для переопределения поведения по умолчанию для удаления изменений разрешений GPO

По мере HF02 элемент РАСШИРЕНного доступа к групповой политики добавил раздел реестра для переопределения поведения разрешений GPO по умолчанию. Дополнительные сведения можно найти в разделе [изменения разрешений объекта групповой политики с помощью расширенного доступа](https://support.microsoft.com/kb/3174540) .

## Статьи по теме


[Расширенное управление групповыми политиками (AGPM)](index.md)

[Новые возможности в AGPM 4.0 с пакетом обновления 3 (SP3)](whats-new-in-agpm-40-sp3.md)

 

 





