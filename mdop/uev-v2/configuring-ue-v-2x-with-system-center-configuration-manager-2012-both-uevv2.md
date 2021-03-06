---
title: Настройка UE-V 2. x с помощью System Center Configuration Manager 2012
description: Настройка UE-V 2. x с помощью System Center Configuration Manager 2012
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824409"
---
# Настройка UE-V 2. x с помощью System Center Configuration Manager 2012


После установки Microsoft User Experience Virtualization (UE-V) 2,0, 2,1 или 2,1 SP1 и их обязательных функций необходимо настроить UE-V. Пакет конфигурации UE-V позволяет администраторам использовать параметры соответствия требованиям компонента System Center Configuration Manager 2012 или более поздней версии для применения согласованных конфигураций на сайтах, где установлены UE-V и Configuration Manager.

## Поддерживаемые функции пакета конфигурации UE-V


Пакет конфигурации UE-V содержит инструменты для выполнения следующих задач:

-   Создание или обновление шаблонов расположений параметров для UE-V.

    -   Определение шаблонов UE-V для регистрации и отмены регистрации

    -   Обновление элементов конфигурации шаблонов UE-V и базовых планов по мере добавления или обновления шаблонов

    -   Распространение и регистрация шаблонов UE-V с помощью стандартных исправлений элементов конфигурации

-   Создание или обновление элемента конфигурации политики агента UE-V для задания или отмены этих параметров.

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Максимальный размер пакета</p></td>
    <td align="left"><p>Включение и отключение синхронизации приложений для Windows</p></td>
    <td align="left"><p>Ожидание синхронизации при запуске приложения</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Настройка задержки импорта</p></td>
    <td align="left"><p>Синхронизация приложений для Windows, не имеющих списка</p></td>
    <td align="left"><p>Ожидание синхронизации при входе</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Уведомление о импорте параметров</p></td>
    <td align="left"><p>URL-адрес контакта</p></td>
    <td align="left"><p>Ожидание тайм-аута синхронизации</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Путь к хранилищу параметров</p></td>
    <td align="left"><p>Описательный текст для контакта</p></td>
    <td align="left"><p>Путь к каталогу шаблонов параметров</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Включение синхронизации</p></td>
    <td align="left"><p>Значок панели включен</p></td>
    <td align="left"><p>Запуск и остановка службы агента UE-V</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Метод синхронизации</p></td>
    <td align="left"><p>Уведомление о первом использовании</p></td>
    <td align="left"><p>Укажите, какие приложения Windows будут перемещаться по параметрам</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Время ожидания синхронизации</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   Проверьте соответствие, убедившись в том, что UE-V запущен.

## Создание элемента конфигурации политики агента UE-V


Все политики и конфигурации агента UE-V распространяются через один элемент конфигурации, созданный с помощью средства UevAgentPolicyGenerator.exe. Это средство считывает необходимую конфигурацию из XML-файла конфигурации и создает CI, содержащий настройки обнаружения и устранения неполадок, необходимые для обеспечения соответствия компьютеру.

CAB-файл, созданный UevTemplateBaselineGenerator.exe с помощью средства командной строки "Настройка политики агента (UE) Agent", имеет следующие параметры:

-   &lt;Код сайта сайта&gt;

-   PolicyName &lt; ( &gt; необязательно): по умолчанию используется значение "политика агента UE-V", если оно отсутствует

-   PolicyDescription &lt; Описание ( &gt; необязательно): предоставляется описание, если оно отсутствует

-   CabFilePath &lt; полный путь к элементу конфигурации. CAB-файл&gt;

-   ConfigurationFile &lt; полный путь к XML-файлу конфигурации агента&gt;

**Примечание**  Возможно, потребуется изменить политику выполнения PowerShell, чтобы разрешить выполнение этих сценариев в среде. В консоли Configuration Manager выполните следующие действия:

1.  Выбор ** &gt; &gt; свойств параметров клиента администрирования**

2.  На вкладке **Агент пользователя** установите для **политики выполнения PowerShell** значение **минуя**

<a href="" id="create"></a>**Создание первого элемента конфигурации политики UE-V**

1.  Скопируйте файл конфигурации по умолчанию из каталога установки UE-V config в расположение, которое видно на консоли администрирования Configuration Manager:

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    Файл конфигурации по умолчанию состоит из пяти разделов.

    <a href="" id="computer-policy"></a>**Политика компьютера**  
    Все параметры уровня компьютера UE-V. Атрибут DesiredState можно

    -   **Назначение значения** в реестре

    -   **Снимите флажки** , чтобы удалить параметр.

    -   **Неуправляемый** , чтобы элемент конфигурации остался в текущем состоянии

    Не удаляйте строки из этого раздела. Вместо этого установите для DesiredState значение "неуправляемая", если Configuration Manager не нужно изменять текущие или значения по умолчанию.

    <a href="" id="currentcomputeruserpolicy"></a>**CurrentComputerUserPolicy**  
    Все параметры пользовательского уровня UE-V. Эти записи переопределяют параметры компьютера для пользователя. Атрибут DesiredState можно

    -   **Назначение значения** в реестре

    -   **Снимите флажки** , чтобы удалить параметр.

    -   **Неуправляемый** , чтобы элемент конфигурации остался в текущем состоянии

    Не удаляйте строки из этого раздела. Вместо этого установите для DesiredState значение "неуправляемая", если Configuration Manager не нужно изменять текущие или значения по умолчанию.

    <a href="" id="services"></a>**Службы**  
    Операции в этом разделе: Служба управления. Файл конфигурации по умолчанию состоит из одной записи для UevAgentService. Для атрибута DesiredState можно установить значение " **выполняется** " или " **остановлено**".

    <a href="" id="windows8appscomputerpolicy"></a>**Windows8AppsComputerPolicy**  
    Все параметры синхронизации приложений для Windows на уровне компьютера. Каждому PackageFamilyName, указанному в этом разделе, можно назначить DesiredState

    -   **Включение** перемещения параметров

    -   **Отключено** для предотвращения перемещения параметров

    -   **Очищено** , что элемент удален из элемента управления UE-V

    В этот раздел можно добавить дополнительные строки на основе списка установленных приложений для Windows, которые можно просмотреть с помощью командлета PowerShell GetAppxPackage.

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**Windows8AppsCurrentComputerUserPolicy**  
    Идентичен Windows8AppsComputerPolicy с параметрами, переопределяющими параметры компьютера для отдельного пользователя.

2.  Измените файл конфигурации, изменив нужные поля состояния и значения.

3.  Выполните эту команду на компьютере, на котором запущена консоль администрирования ConfigMgr:

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  Импорт CAB-файла с помощью консоли ConfigMgr или импорта PowerShell — CMConfigurationItem

**Обновление элемента конфигурации политики UE-V**

1.  Измените файл конфигурации, изменив нужные поля состояния и значения.

2.  Выполните команду, указанную на шаге 3, в разделе [Создание первого элемента конфигурации политики UE-V](#create). Если вы изменили имя с помощью параметра PolicyName, убедитесь, что вы ввели то же имя.

3.  Повторно импортируйте CAB-файл. Версия Configuration Manager будет обновлена.

## Создание базового шаблона UE-V
Шаблоны UE-V распространяются с помощью базового плана, содержащего несколько элементов конфигурации. Каждый элемент конфигурации включает сценарии обнаружения и устранения неполадок, необходимые для установки одного шаблона UE-V. Реальный шаблон UE-V внедрен в сценарий исправления для распространения с помощью стандартных функций элемента конфигурации.

Базовый шаблон UE-V создается с помощью средства командной строки UevTemplateBaselineGenerator.exe, которое имеет следующие параметры:

-   &lt;Код сайта сайта&gt;

-   BaselineName &lt; имя &gt; (необязательно: по умолчанию — "UE-V Template дистрибутив Baseline", если не указано)

-   &lt;Описание BaselineDescription &gt; (необязательно: описание предоставляется, если оно отсутствует)

-   &lt;Папка шаблонов UE-V TemplateFolder&gt;

-   Зарегистрировать &lt; список файлов шаблонов, разделенных запятыми&gt;

-   Отмена регистрации &lt; списка шаблонов, разделенных запятыми&gt;

-   CabFilePath &lt; полный путь к создаваемому шаблону CAB-файла&gt;

Результат — это исходный CAB-файл, который готов для импорта в Configuration Manager. Если вы обновляете или добавляете шаблон в будущем, вы можете повторно выполнить команду с тем же именем базового плана. Импорт CAB-файла приводит к обновлению версии CI на измененных шаблонах.

### <a href="" id="create2"></a>Создание первого базового шаблона для UE-V

1.  Создайте набор шаблонов UE-V в стабильном расположении папки, видимой для компьютера, на котором работает консоль администратора ConfigMgr. По мере добавления или обновления шаблонов в этой папке они будут извлечены для распространения. Начальный список шаблонов можно скопировать с компьютера, на котором установлен UE-V. Расположение шаблона по умолчанию — C:\\program Files Files\\Microsoft взаимодействие с пользователем Virtualization\\Templates.

2.  Создайте файл text.bat, в который вы можете добавить команду генератора шаблонов. Это необязательно, но создание повторного создания будет проще, если сохранить параметры команды.

3.  Добавьте команду и параметры в bat – файл, который будет создавать базовый план. В следующем примере создается базовый план, который распределяет блокноты и калькулятор.

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  Запустите bat – файл, чтобы создать UevTemplateBaseline.cab готовы для импорта в Configuration Manager.

### Обновление базового шаблона UE-V

Генератор шаблонов использует версию шаблона, чтобы определить, нужно ли обновлять шаблон. Если вы изменяете шаблон и обновляете версию, базовый генератор сравнивает шаблон в главной папке с шаблоном, который содержится в CI на сервере Configuration Manager. При обнаружении разницы обновляются сформированный базовый план и измененные версии CI.

Чтобы распространить новый шаблон блокнота, выполните указанные ниже действия.

1.  Обновите шаблон и версию шаблона, расположенные &lt; в &gt; элементе Version шаблона.

2.  Скопируйте шаблон в основной каталог шаблонов.

3.  Выполните команду в файле. bat, созданном на этапе 3, в разделе [Создание первого базового шаблона UE-V](#create2).

4.  Импортируйте созданный CAB-файл в Configuration Manager с помощью консоли или импортной оболочки PowerShell — CMBaseline.

## Получение пакета конфигурации UE-V


Пакет конфигурации UE-V для Configuration Manager 2012 с пакетом обновления 1 (SP1) или более поздней версии можно загрузить [здесь](https://go.microsoft.com/fwlink/?LinkId=317263).






## Статьи по теме


[Управление конфигурациями UE-V 2.x](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





