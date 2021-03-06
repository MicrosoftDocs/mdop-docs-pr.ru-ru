---
title: Планирование развертывания программы Sequencer и клиента App-V 5.0
description: Планирование развертывания программы Sequencer и клиента App-V 5.0
author: dansimp
ms.assetid: 57a604ad-90e1-4d32-86bb-eafff59aa43a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8c6f7c4d717acad014f079e51a7013a57766d9ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813464"
---
# Планирование развертывания программы Sequencer и клиента App-V 5.0


Прежде чем приступить к работе с Microsoft Application Virtualization (App-V) 5,0, необходимо установить секвенсор App-v 5,0, клиент App-V 5,0 и, возможно, общее хранилище содержимого App-V 5,0. В следующих разделах Планирование рассматриваются для этих установок.

## Планирование развертывания App-V 5,0 Sequencer


Приложение App-V 5,0 использует процесс, называемый виртуализацией, для создания виртуализированных приложений и пакетов приложений. Для виртуализации требуется использование компьютера, на котором работает секвенсор App-V 5,0.

**Примечание**  Сведения о новых возможностях приложения App-V 5,0 можно найти в разделе " **изменения" раздела "** новые возможности" [в приложении app-v 5,0](whats-new-in-app-v-50.md).

 

Компьютер, на котором работает секвенсор App-V 5,0, должен соответствовать минимальным системным требованиям. Список требований можно найти в разделе [Поддерживаемые конфигурации App-V 5,0](app-v-50-supported-configurations.md).

В идеале программа Sequencer должна быть установлена на компьютере, работающем под управлением виртуальной машины. Это позволяет более легко вернуть компьютер, на котором работает секвенсор, в состояние очистки перед виртуализацией другого приложения. При установке секвенсора с помощью виртуальной машины необходимо выполнить следующие действия:

1.  Установите все связанные необходимые компоненты программы Sequencer.

2.  Установите секвенсор.

3.  Сделайте "снимок" среды.

**Важно!**  Вы должны иметь корпоративную проверку группы корпоративной безопасности и утвердить план обработки последовательности. По соображениям безопасности следует хранить операции Sequencer в лаборатории, отдельном от производственной среды. Разделение на цветоделение может быть как простым, так и полным, в зависимости от требований бизнеса. Компьютеры виртуализации должны иметь возможность подключаться к корпоративной сети, чтобы копировать завершенные пакеты на производственные серверы. Тем не менее, так как компьютеры последовательности обычно работают без защиты от вирусов, они не должны входить в корпоративную сеть, не защищенную паролем. Например, вы можете работать в брандмауэре или сегменте изолированной сети. Вы также можете использовать виртуальные машины, настроенные для предоставления общего доступа к изолированной виртуальной сети. Следуйте своим корпоративным политикам безопасности, чтобы безопасно решить эти проблемы.

 

[Установка программы Sequencer](how-to-install-the-sequencer-beta-gb18030.md)

## Планирование развертывания клиента App-V 5,0


Для выполнения виртуализированных пакетов на целевых компьютерах необходимо установить клиент App-V 5,0 на целевые компьютеры. Клиент App-V 5,0 является компонентом, который запускает виртуализированное приложение на целевом компьютере. Клиент позволяет пользователям взаимодействовать со значками и определенными типами файлов для запуска виртуализированных приложений. Кроме того, клиент помогает получить содержимое приложения с сервера управления и кэширует содержимое, прежде чем клиент запустит приложение. Существует два разных типа клиентов: клиент для служб удаленных рабочих столов, который используется на серверных системах (узле сеансов удаленных рабочих столов) и клиенте App-V 5,0, который используется для всех остальных компьютеров.

Клиент App-V 5,0 следует настроить с помощью командной строки установщика либо с помощью сценария PowerShell после завершения установки.

Для ускорения развертывания клиентского программного обеспечения App-V 5,0 необходимо заранее определить параметры. Это особенно важно, если у вас есть компьютеры в разных офисах, где необходимо настроить для них использование разных расположений.

Кроме того, необходимо определить, как будет развертываться клиентское программное обеспечение. Несмотря на то, что вы можете развернуть клиент вручную на каждом компьютере, большинство организаций предпочитают развертывание клиента с помощью автоматизированного процесса. В более крупной организации может быть установлена операционная система многофункционального распространения программного обеспечения (ESD) — идеальная клиентская система развертывания. Если система ESD не существует, вы можете использовать стандартный способ установки программного обеспечения своей организации. Возможные методы включают в себя групповую политику или различные методики создания сценариев. В зависимости от количества и разнородных местоположений на клиентских компьютерах этот процесс развертывания может быть сложным. Необходимо использовать структурированный подход, чтобы убедиться, что на всех компьютерах установлен клиент с правильной конфигурацией.

Список минимальных требований клиента см. в разделе [требования к приложению App-V 5,0](app-v-50-prerequisites.md).

[Развертывание клиента App-V](how-to-deploy-the-app-v-client-gb18030.md)

## <a href="" id="bkmk-client-coexist"></a>Планирование сосуществования клиента App-V


Вы можете развернуть клиент App-V 5,0 в клиенте App-V 4,6 на стороне клиента. Для обеспечения совместимости с клиентом необходимо добавить или опубликовать виртуализированные приложения с помощью файла конфигурации развертывания или файла конфигурации пользователя, так как в этих файлах конфигурации есть определенные параметры, которые необходимо настроить, чтобы приложение App-V 5,0 работает с клиентами App-V 4.6. При обновлении пакета с помощью клиента или сервера пакет должен повторно отправить файл конфигурации. Это справедливо для любого пакета, который имеет соответствующий файл конфигурации, поэтому он не специфичен для сосуществования клиентов. Тем не менее, если вы не отправили файл конфигурации во время обновления пакета, состояние пакета не будет работать должным образом в сценариях сосуществования.

Файлы динамических конфигураций App-V 5,0 настройте пакет для определенного пользователя. Перед использованием файла динамической конфигурации пользователя (XML) или динамической конфигурации развертывания необходимо создать его. Чтобы создать файл, необходимо выполнить расширенную операцию вручную.

При использовании динамического файла пользовательской конфигурации никакие сведения о App-V 5,0 для расширения в файле манифеста не используются. Это означает, что файл динамической конфигурации пользователя должен содержать все для расширения, специфического для App-V 5,0 в файле манифеста, а также изменения, которые вы хотите внести, такие как удаления и обновления. Дополнительные сведения о том, как создать настраиваемый файл конфигурации, приведены [в разделе Создание настраиваемого файла конфигурации с помощью консоли управления App-V 5,0](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md).

[Развертывание приложения App-V 4,6 и клиента App-V 5,0 на том же компьютере](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

## <a href="" id="bkmk-plan-for-scs"></a>Планирование хранилища общего содержимого для App-V 5,0 (SCS)


Режим хранилища общего содержимого для App-V 5,0 позволяет компьютеру с запущенным клиентом App-V 5,0 запускать виртуализированные приложения, но ни одно из содержимого пакета не сохраняется на компьютере, на котором запущен клиент App-V 5,0. Виртуальные приложения переносятся в поток на целевые компьютеры только по запросу клиента.

В следующем списке приведены некоторые преимущества использования хранилища общего содержимого App-V 5,0.

-   Снижены конфликты приложений между приложениями и многопоточными приложениями, и, следовательно, меньше требуется тестирование регрессии

-   Ускоренное развертывание приложений с целью снижения риска развертывания

-   Упрощенное управление профилями

[Установка клиента App-V 5.0 для режима хранилища общего содержимого](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)






## <a href="" id="other-resources-for-the-app-v-5-0-deployment-"></a>Другие ресурсы по развертыванию App-V 5,0


[Планирование развертывания App-V](planning-to-deploy-app-v.md)

 

 





