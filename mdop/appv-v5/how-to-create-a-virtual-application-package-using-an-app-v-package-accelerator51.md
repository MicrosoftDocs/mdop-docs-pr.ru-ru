---
title: Создание пакета виртуального приложения с помощью ускорителя пакетов App-V
description: Создание пакета виртуального приложения с помощью ускорителя пакетов App-V
author: dansimp
ms.assetid: eae1e4f8-f14f-4bc8-9867-052561c37297
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 15376ae52a19b2d220f9ea0031f3ad5649ca487d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814272"
---
# Создание пакета виртуального приложения с помощью ускорителя пакетов App-V


**Важно.**  
Приложение App-V 5,1 не предоставляет никаких прав лицензии на программное обеспечение, которое вы используете для создания ускорителя пакетов. Вы должны соблюдать все условия лицензионного соглашения конечного пользователя для используемого приложения. Ответственность за то, что условия лицензионного соглашения на использование программного обеспечения позволяют создать пакетный ускоритель с помощью приложения Application-V 5,1 Sequencer.



Чтобы создать пакет виртуального приложения с ускорителем пакетов App-V 5,1, выполните указанные ниже действия.

**Примечание.**  
Прежде чем приступать к этой процедуре, скопируйте необходимый ускоритель пакетов на компьютер, на котором работает секвенсор App-V 5,1. Кроме того, необходимо скопировать все необходимые файлы установки для пакета в локальный каталог на компьютере, на котором работает секвенсор. Это каталог, который нужно задать в действии 5 этой процедуры.



**Создание виртуального пакета приложения с ускорителем пакетов приложения App-V 5,1**

1.  Для запуска секвенсора App-v на компьютере, на котором работает секвенсор App-v 5,1, нажмите кнопку **запустить**  /  **все программы**  /  **Microsoft**Application Virtualization  /  **Sequencer Microsoft Applications**.

2.  Чтобы запустить **Мастер создания пакета**, нажмите **создать новый виртуальный пакет приложения**. Чтобы создать пакет, установите флажок **создать пакет с помощью ускорителя пакетов** и нажмите кнопку **Далее**.

3.  Чтобы указать ускоритель пакетов, который будет использоваться для создания нового виртуального пакета приложения, нажмите кнопку **Обзор** на странице **Выбор ускорителя пакетов** . Нажмите кнопку **Далее**.

    **Важно.**  
    Если издатель ускорителя пакетов не может пройти проверку и не содержит действительной цифровой подписи, перед нажатием кнопки **выполнить**необходимо подтвердить, что вы доверяете источнику ускорителя пакетов. Подтвердите выбор в диалоговом окне " **предупреждение системы безопасности** ".



4.  На странице " **руководство** " ознакомьтесь со сведениями о публикации, которые отображаются в области сведений. Эта информация была добавлена при создании ускорителя пакетов и содержит руководство по созданию и публикации пакета. Чтобы экспортировать сведения о руководстве в текстовый файл (txt), нажмите кнопку **Экспорт** и укажите расположение, в котором нужно сохранить файл, и нажмите кнопку **Далее**.

5.  На странице **Выбор установочных файлов** выберите команду создать **папку** , чтобы создать локальную папку, содержащую все необходимые файлы установки пакета, и укажите, где следует сохранить папку. Кроме того, необходимо указать имя, которое будет назначаться папке. Затем необходимо скопировать все необходимые файлы установки в указанное вами расположение. Если папка, содержащая установочные файлы, уже существует на компьютере, на котором работает секвенсор, нажмите кнопку **Обзор** , чтобы выбрать папку.

    Кроме того, если вы уже скопировали файлы установки в каталог на этом компьютере, щелкните **создать папку**, перейдите в папку, содержащую установочные файлы, и нажмите кнопку **Далее**.

    **Примечание.**  
    Вы можете указать следующие типы файлов, которые поддерживаются при установке:

    -   Файлы установщика Windows (**MSI**)

    -   САВ-файлы (CAB)

    -   Сжатые файлы с расширением имени ZIP-файла

    -   Файлы реальных приложений

    Следующие типы файлов не поддерживаются: **MSP** и **exe** . Если указан **exe** – файл, необходимо извлечь установочные файлы вручную.



~~~
If the package accelerator requires an application to be installed before you apply the Package Accelerator, and if you have already installed the required application, select **I have installed all applications**, and then click **Next** on the **Local Installation** page.
~~~

6. На странице **имя пакета** укажите имя, которое будет сопоставлено с пакетом. Указанное имя определяет пакет в консоли управления App-V. Нажмите кнопку **Далее**.

7. На странице " **Создание пакета** " Введите примечания, которые будут связаны с пакетом. Примечания должны содержать идентификационные данные о создаваемом пакете. Для подтверждения места создания пакета ознакомьтесь со сведениями, которые отображаются в **папке для сохранения**. Чтобы сжать пакет, выберите пункт **сжать пакет**. Установите флажок **сжимать пакет** , если пакет будет передаваться по сети или если размер пакета ПРЕВЫШАЕТ 4 ГБ.

   Чтобы создать пакет, нажмите кнопку **создать**. После создания пакета нажмите кнопку **Далее**.

8. На странице " **Настройка программного обеспечения** " для включения секвенсора для настройки приложений, входящих в пакет, выберите пункт " **Настройка программного обеспечения**". На этом этапе можно настроить все связанные задачи, которые необходимо выполнить, чтобы запустить приложение на целевом компьютере. Например, вы можете настроить любые связанные лицензионные соглашения.

   Если выбрать параметр **настроить программное обеспечение**, можно настроить следующие элементы с помощью секвенсора в рамках этого этапа:

   -   **Загрузить пакет**. Программа Sequencer загружает файлы, связанные с пакетом. Декодирование пакета может занять от нескольких секунд до часа.

   -   **Запустите каждую программу**. При необходимости запустите программы, содержащиеся в пакете. Этот этап полезен для выполнения связанных с ним лицензий или задач настройки, которые необходимы для запуска приложения перед развертыванием и запуском пакета на целевом компьютере. Чтобы запустить сразу все программы, выберите по крайней мере одну программу, а затем нажмите кнопку **выполнить все**. Чтобы запустить определенные программы, выберите программу или программы, которые вы хотите запустить, и нажмите кнопку **выполнить выбрано**. Заполните необходимые задачи настройки, а затем закройте приложения. Для запуска всех программ может потребоваться несколько минут. Нажмите кнопку **Далее**.

   -   **Сохранить пакет**. Секвенсор сохраняет пакет.

   -   **Основной блок функций**. Секвенсор оптимизирует пакет для потоковой передачи, перестраивая основной блок функций.

   Если вы не хотите настраивать приложения, нажмите **пропустить этот шаг**и перейдите к действию 9, а затем нажмите кнопку **Далее**.

9. На странице **завершения** после просмотра данных, отображаемых в области **отчета о пакетах виртуальных приложений** , нажмите кнопку **Закрыть**.

   Пакет теперь доступен в секвенсоре. Чтобы изменить свойства пакета, нажмите **изменить \ [имя пакета \]**. Дополнительные сведения о том, как изменить пакет, приведены [в разделе Изменение существующего виртуального пакета приложения](how-to-modify-an-existing-virtual-application-package-beta.md).

   **У вас есть предложение App-V**? Здесь вы можете добавить предложения и проголосовать [здесь](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **У вас возникла ошибка App-V?** Используйте [Форум TechNet App-V](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).

## Статьи по теме


[Операции, связанные с администрированием и использованием App-V 5.1](operations-for-app-v-51.md)









