---
title: Использование портала службы поддержки
description: Использование портала службы поддержки
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826329"
---
# Использование портала службы поддержки


Веб-сайт администрирования и мониторинга MBAM, также называемый порталом службы поддержки, — это административный интерфейс для шифрования диска BitLocker, установленный как часть инфраструктуры сервера администрирования Microsoft BitLocker и мониторинга (MBAM). В следующих разделах описано, как с помощью этого веб-сайта можно просматривать отчеты, восстанавливать диски конечных пользователей и управлять доверенными платформенными модулями конечных пользователей.

## <a href="" id="bkmk-reports"></a>Отчеты


MBAM собирает данные из службы каталогов Active Directory и клиентских компьютеров, что позволяет запускать различные отчеты для мониторинга использования и соответствия требованиям BitLocker. С помощью раздела **отчеты** на веб-сайте администрирования и мониторинга вы можете создавать отчеты о соответствии требованиям предприятия, отдельных компьютерах и действиях по восстановлению ключей. Описание каждого отчета можно найти в разделе [Общие сведения о MBAM](understanding-mbam-reports-mbam-2.md).

**Получение доступа к отчетам**

1.  Откройте веб-браузер и перейдите на веб-сайт администрирования и мониторинга MBAM.

2.  В левой области выберите пункт **отчеты** .

3.  В верхней строке меню выберите тип отчета, который вы хотите создать. Чтобы сохранить отчет, нажмите кнопку " **Экспорт** " в строке меню "отчеты".

Дополнительные сведения о том, как выполнять MBAM отчеты, приведены [в разделе Создание отчетов MBAM](how-to-generate-mbam-reports-mbam-2.md).

## <a href="" id="bkmk-drirec"></a>Восстановление диска


Функция **восстановления дисков** на веб-сайте администрирования и мониторинга позволяет пользователям с определенными ролями администратора (например, пользователям службы технической поддержки) получать данные ключа восстановления, собранные клиентом MBAM. Эти данные можно использовать для доступа к диску, защищенному BitLocker, при переходе BitLocker в режим восстановления. Инструкции по восстановлению диска, который находится в режиме восстановления, приведены в разделе [Восстановление диска в режиме восстановления](how-to-recover-a-drive-in-recovery-mode-mbam-2.md).

Вы также можете восстановить диски, которые были перемещены или повреждены.

-   [Восстановление перемещенного диска](how-to-recover-a-moved-drive-mbam-2.md)

-   [Восстановление поврежденного диска](how-to-recover-a-corrupted-drive-mbam-2.md)

Дополнительные сведения о том, как восстановить защищенный BitLocker диск, можно найти [в разделе Выполнение управления BitLocker с помощью MBAM](performing-bitlocker-management-with-mbam-mbam-2.md).

## <a href="" id="bkmk-manatpm"></a>Управление TPM


Функция управления TPM на веб-сайте администрирования и мониторинга позволяет пользователям с определенными ролями администратора (например, "Пользователи службы поддержки MBAM") получать доступ к данным доверенного платформенного модуля, собранным клиентом MBAM. В случае блокировки доверенного платформенного модуля администратор может использовать веб-сайт администрирования и наблюдения для извлечения необходимого файла пароля, чтобы разблокировать доверенный платформенный модуль. Инструкции по сбросу доверенного платформенного модуля после блокировки ДОВЕРЕНного платформенного модуля приведены [в разделе Сброс блокировки доверенного платформенного](how-to-reset-a-tpm-lockout-mbam-2.md)модуля.

## <a href="" id="bkmk-helpdesk"></a> MBAM задач службы поддержки


Вы можете использовать веб-сайт администрирования и наблюдения для множества административных задач, таких как управление оборудованием, защищенным с помощью BitLocker, восстановление дисков и запуск отчетов. По умолчанию URL-адрес сайта администрирования и мониторинга — http:// &lt; *MBAMAdministrationServername* &gt; , но его можно настроить в процессе установки.

**Примечание**  Для доступа к различным функциям, предоставляемым веб-сайтом администрирования и наблюдения, необходимо иметь соответствующие роли, связанные с вашей учетной записью пользователя. Дополнительные сведения о ролях пользователей можно найти в разделе [Управление ролями администратора MBAM](how-to-manage-mbam-administrator-roles-mbam-2.md).

 

Ниже приведены ссылки на дополнительные сведения о задачах, которые можно выполнять с помощью веб-сайта администрирования и мониторинга.

-   [Сброс блокировки доверенного платформенного модуля](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [Восстановление диска в режиме восстановления](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [Восстановление перемещенного диска](how-to-recover-a-moved-drive-mbam-2.md)

-   [Восстановление поврежденного диска](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [Определение состояния шифрования BitLocker утерянных компьютеров](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





