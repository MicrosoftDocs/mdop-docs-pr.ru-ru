---
title: Виртуализация нового приложения с помощью App-V 5.0
description: Виртуализация нового приложения с помощью App-V 5.0
author: dansimp
ms.assetid: a263fa84-cd6d-4219-a5c2-eb6a553b826c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 13fdda066f79d918da1970e0cab6c1d6e60f6585
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813720"
---
# Виртуализация нового приложения с помощью App-V 5.0


**Просмотр и подготовка перед началом последовательности**

1.  Определите тип виртуализированного пакета приложения, который вы хотите создать:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Тип приложения</th>
    <th align="left">Описание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Standard</p></td>
    <td align="left"><p>Создает пакет, содержащий приложение или набор приложений. Этот параметр является предпочтительным для большинства типов приложений.</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Надстройка или плагин</p></td>
    <td align="left"><p>Создает пакет, который расширяет функциональные возможности стандартного приложения, например плагин для Microsoft Excel. Кроме того, вы можете использовать подключаемые модули для приложений, установленных в собственном коде, или для другого пакета, связанного с помощью групп подключения.</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Старые</p></td>
    <td align="left"><p>Создает пакет, который необходим стандартному приложению, например Java. Пакеты по промежуточного слоя используются для связывания с другими пакетами с помощью групп подключений.</p></td>
    </tr>
    </tbody>
    </table>



2.  Скопируйте все необходимые файлы установки на компьютер, на котором работает секвенсор.

3.  Создайте резервную копию виртуальной среды перед виртуализацией приложения, а затем вернитесь к этому образу каждый раз после завершения виртуализации приложения.

4.  Просматривайте следующие элементы:

    -   Если установщик приложения изменяет безопасный доступ к новому или существующему файлу или каталогу, эти изменения не фиксируются в пакете.

    -   Если для целевого тома виртуализированного пакета отключены короткие пути, необходимо также попытаться поочередно задать пакет для созданного тома, по-прежнему отключены короткие пути. Это не может быть системный том.

    -   Начиная с версии App-V 5,0 SP3, основной каталог виртуального приложения (PVAD) скрыт, но вы можете включить его снова. Дополнительные [сведения о приложении App-V 5,0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).

**Создание последовательности нового стандартного приложения**

1.  На компьютере с программой Sequencer выберите **все программы**, а затем — **Виртуализация приложений**Microsoft, а затем выберите **Microsoft Application Virtualization Sequencer**.

2.  В секвенсоре щелкните **создать новый виртуальный пакет приложения**. Выберите команду **создать пакет (по умолчанию)**, а затем нажмите кнопку **Далее**.

3.  На странице **Подготовка компьютера** изучите проблемы, которые могут привести к сбою при создании пакета или привести к тому, что пакет может содержать ненужные данные. Прежде чем продолжить, устраните все возможные проблемы. После внесения исправлений нажмите кнопку **Обновить** , чтобы отобразить обновленные сведения. После устранения всех возможных проблем нажмите кнопку **Далее**.

    **Важно.**  
    Если вы хотите отключить антивирусную программу, необходимо сначала проверить компьютер, на котором работает секвенсор, чтобы убедиться в том, что нежелательные или вредоносные файлы не могут быть добавлены в пакет.



4.  На странице **Тип приложения** установите флажок **стандартное приложение (по умолчанию)** и нажмите кнопку **Далее**.

5.  На странице " **Выбор установщика** " нажмите кнопку **Обзор** и укажите файл установки для приложения.

    **Примечание.**  
    Если указанный установщик приложения изменяет безопасность доступа к файлу или папке, существующим или новым, связанные изменения не будут записаны в пакет.



~~~
If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.
~~~

6. На странице " **имя пакета** " введите имя, которое будет сопоставлено с пакетом. Используйте имя, которое помогает идентифицировать цель и версию приложения, которые будут добавлены в пакет. Имя пакета отобразится в консоли управления App-V 5,0.

   **Основной каталог виртуальных приложений** отображает путь, по которому приложение будет установлено на конечных компьютерах. Чтобы указать это расположение, нажмите кнопку **Обзор**.

   **Примечание.**  
   Начиная с версии App-V 5,0 SP3, основной каталог виртуального приложения (PVAD) скрыт, но вы можете включить его снова. Дополнительные [сведения о приложении App-V 5,0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).



~~~
**Important**  
The primary application virtual directory should match the installation location for the application that is being sequenced. For example, if you install Notepad to **C:\\Program Files\\Notepad**; you should configure **C:\\Program Files\\Notepad** as your primary virtual directory. Alternatively, you can choose to set **C:\\Notepad** as the primary virtual application directory, as long as during installation time, you configure the installer to install to **C:\\Notepad**. Editing the Application Virtualization path is an advanced configuration task. For most applications, the default path is recommended for the following reasons:

-   Application Compatibility. Some virtualized applications will not function correctly, or will fail to open if the directories are not configured with identical virtual directory paths.

-   Performance. Since no file system redirection is required, the runtime performance can improve.



**Tip**  
It is recommended that prior to Sequencing an application, you open the associated installer to determine the default installation directory, and then configure that location as the **Primary Virtual Application Directory**.



Click **Next**.
~~~

7. На странице **установки** , когда секвенсор и установщик приложения готовы, вы можете продолжить установку приложения, чтобы секвенсор мог отслеживать процесс установки.

   **Важно.**  
   Вы должны всегда устанавливать приложения в безопасном месте и не можете войти в систему на компьютере, на котором запущены программы Sequencer во время наблюдения.



~~~
Use the application's installation process to perform the installation. If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files. When you are finished with the installation, select **I am finished installing**. Click **Next**.
~~~

8. На странице **установки** подождите, пока секвенсор настроит пакет виртуализированного приложения.

9. На странице **Настройка программного обеспечения** при необходимости запустите программы, содержащиеся в пакете. Этот шаг позволяет выполнить необходимые задачи лицензирования или настройки перед развертыванием и запуском пакета на целевом компьютере. Чтобы запустить все программы за один раз, выберите хотя бы одну программу, а затем нажмите кнопку **выполнить все**. Чтобы запустить определенные программы, выберите программу или программы, а затем выберите команду **выполнить выбрано**. Заполните необходимые задачи настройки и закройте приложения. Возможно, потребуется подождать несколько минут, пока все программы не будут запущены.

   **Примечание.**  
   Чтобы выполнить задачи при первом использовании для любого приложения, которое не доступно в списке, откройте приложение. На этом этапе будут собраны соответствующие сведения.



~~~
Click **Next**.
~~~

10. На странице **отчета об установке** можно просмотреть сведения о виртуализированном пакете приложения, который вы только что посвящены. В **дополнительных сведениях**дважды щелкните событие, чтобы получить более подробные сведения. Чтобы продолжить, нажмите кнопку **Далее**.

11. Откроется страница **настройки** . Если вы закончите установку и настройку виртуального приложения, нажмите кнопку **остановить сейчас** и перейдите к шагу 14 этой процедуры. Чтобы выполнить любое из указанных ниже действий, нажмите кнопку **настроить**.

    -   Подготовьте виртуальный пакет для потоковой передачи. Потоковая передача повышает удобство работы с виртуальным пакетом приложения на целевом компьютере.

    -   Укажите операционные системы, которые могут запускать этот пакет.

    Нажмите кнопку **Далее**.

12. На странице **потоковой передачи** запустите каждую программу, чтобы ее можно было оптимизировать и эффективно работать на конечных компьютерах. Выполнение всех приложений может занять несколько минут. После запуска всех приложений закройте все приложения и нажмите кнопку **Далее**.

   **Примечание.**  
   Если вы не откроете какие-либо приложения на этом этапе, потоковая передача по умолчанию будет доставлять по запросу. Это означает, что приложения будут загружаться по битам, пока он не будет открыт, а затем, в зависимости от того, как настроена Фоновая загрузка, будет загружаться оставшаяся часть приложения.



13. На странице **Целевая операционная** система укажите операционные системы, которые могут запускать этот пакет. Чтобы разрешить запуск этого пакета для всех поддерживаемых операционных систем в среде, установите флажок **Разрешить запуск этого пакета в любой операционной системе**. Чтобы настроить выполнение этого пакета только в определенных операционных системах, установите флажок **Разрешить запуск этого пакета только в указанных ниже операционных системах** и выберите операционные системы, которые могут запускать этот пакет. Нажмите кнопку **Далее**.

   **Важно.**  
   Убедитесь в том, что указанные здесь операционные системы поддерживаются в приложении, которое вы используете в качестве последовательности.



14. Откроется страница " **Создание пакета** ". Чтобы изменить пакет, не сохраняя его, нажмите кнопку **продолжить, чтобы изменить пакет без сохранения с помощью редактора пакетов**. Этот параметр открывает пакет на консоли секвенсор, чтобы можно было изменить пакет перед сохранением. Нажмите кнопку **Далее**.

   Чтобы сохранить пакет немедленно, выберите **сохранить пакет** (по умолчанию). Добавьте **Комментарии** , которые должны быть связаны с пакетом. Комментарии полезны для определения версии программы и другой информации о пакете.

   **Важно.**  
   Система не поддерживает непечатаемые символы в **комментариях** и **описаниях**.



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

15. Откроется страница **завершения** . При необходимости просмотрите сведения в области **отчета о пакетах виртуальных приложений** и нажмите кнопку **Закрыть**. Эти сведения также доступны в файле **Report.xml** , который находится в каталоге, в котором был создан пакет.

   Пакет теперь доступен в секвенсоре.

   **Важно.**  
   После того как вы успешно создадите виртуальный пакет приложения, вы не сможете запустить виртуальный пакет приложения на компьютере, на котором запущен секвенсор.



**Упорядочение надстройки или внешнего приложения**

1.  

    **Примечание.**  
    Перед выполнением описанной ниже процедуры установите родительское приложение локально на компьютере, на котором запущен секвенсор. Или, если у вас есть виртуализированное родительское приложение, вы можете выполнить действия, описанные в рабочем процессе надстройки или плагина, чтобы распаковать родительское приложение на компьютере.

    Например, если вы подключаете плагин для Microsoft Excel, установите Microsoft Excel локально на компьютере, на котором запущен секвенсор. Также установите родительское приложение в том же каталоге, где установлен приложение на целевом компьютере. Если плагин или надстройка будут использоваться с существующим пакетом виртуального приложения, установите приложение на тот же виртуальный диск, который использовался при создании родительского пакета виртуальных приложений.



~~~
On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.
~~~

2. *<strong><em>В секвенсоре щелкните * </em> создать новый виртуальный пакет приложения </strong> . Выберите команду **создать пакет (по умолчанию)**, а затем нажмите кнопку **Далее**.

3. На странице **Подготовка компьютера** изучите проблемы, которые могут привести к сбою при создании пакета или привести к тому, что пакет может содержать ненужные данные. Прежде чем продолжить, устраните все возможные проблемы. После внесения исправлений нажмите кнопку **Обновить** , чтобы отобразить обновленные сведения. После устранения всех возможных проблем нажмите кнопку **Далее**.

   **Важно.**  
   Если вы хотите отключить антивирусную программу, необходимо сначала проверить компьютер, на котором работает секвенсор, чтобы убедиться в том, что нежелательные или вредоносные файлы не могут быть добавлены в пакет.



4. На странице " **Тип приложения** " выберите **надстройку или плагин**и нажмите кнопку **Далее**.

5. На странице " **Выбор установщика** " нажмите кнопку **Обзор** и укажите установочный файл для надстройки или плагина. Если у надстройки нет связанного файла установщика и вы планируете выполнить все инструкции по установке вручную, установите флажок **выбрать этот параметр, чтобы выполнить выборочную установку** , и нажмите кнопку **Далее**.

6. На **главной странице установки** убедитесь, что на компьютере, на котором запущена программа Sequencer, установлено основное приложение. Кроме того, вы можете расширить существующий пакет, сохраненный локально на компьютере, на котором работает секвенсор. Для этого щелкните **развернуть пакет**и выберите пакет. После развертывания или установки родительской программы установите флажок **я установил основную родительскую программу**.

   Нажмите кнопку **Далее**.

7. На странице " **имя пакета** " введите имя, которое будет сопоставлено с пакетом. Используйте имя, которое помогает идентифицировать цель и версию приложения, которые будут добавлены в пакет. Имя пакета будет отображаться в консоли управления App-V 5,0. **Основной каталог виртуальных приложений** отображает путь, по которому будет установлено приложение. Чтобы указать это расположение, введите путь или нажмите кнопку **Обзор**.

   **Примечание.**  
   Начиная с версии App-V 5,0 SP3, основной каталог виртуального приложения (PVAD) скрыт, но вы можете включить его снова. Дополнительные [сведения о приложении App-V 5,0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).



~~~
Click **Next**.
~~~

8. На странице **установки** , когда секвенсор и установщик приложения готовы, вы можете продолжить установку плагина или надстройки, чтобы программа Sequencer могла отслеживать процесс установки. Используйте процесс установки приложения для выполнения установки. Если в процессе установки необходимо запустить дополнительные файлы установки, нажмите кнопку **выполнить** , найдите и запустите дополнительные файлы установки. Когда вы закончите установку, выберите параметр **Установка завершена**, а затем нажмите кнопку **Далее**.

9. На странице **отчета об установке** можно просмотреть сведения о пакете виртуального приложения, который вы только что посвящены. Чтобы получить более подробное описание сведений, отображаемых в **дополнительных сведениях**, дважды щелкните событие. После того как вы проверили данные, нажмите кнопку **Далее**.

10. Откроется страница **настройки** . Если вы закончите установку и настройку виртуального приложения, нажмите кнопку **остановить сейчас** и перейдите к шагу 12 этой процедуры. Чтобы выполнить любое из указанных ниже действий, нажмите кнопку **настроить**.

    -   Оптимизируйте работу пакета в медленной или ненадежной сети.

    -   Укажите операционные системы, которые могут запускать этот пакет.

    Нажмите кнопку **Далее**.

11. На странице **потоковой передачи** запустите каждую программу, чтобы ее можно было оптимизировать и эффективно работать на конечных компьютерах. Потоковая передача повышает удобство работы с виртуальным пакетом приложений на конечных компьютерах в сетях с большим временем задержки. Выполнение всех приложений может занять несколько минут. После запуска всех приложений закройте каждое из них. Кроме того, вы можете настроить пакет так, чтобы он был полностью скачан перед открытием, выбрав флажок **заставлять приложения для загрузки** . Нажмите кнопку **Далее**.

   **Примечание.**  
   При необходимости вы можете остановить загрузку приложения на этом этапе. В диалоговом окне **Запуск приложения** нажмите кнопку **остановить** и установите один из флажков: **остановить все приложения** или **остановить только это приложение**.



12. На странице **Целевая операционная** система укажите операционные системы, которые могут запускать этот пакет. Чтобы разрешить запуск этого пакета для всех поддерживаемых операционных систем в вашей среде, установите флажок **Разрешить выполнение этого пакета для любой операционной системы** . Чтобы настроить запуск этого пакета только в определенных операционных системах, установите флажок **Разрешить запуск этого пакета только на указанных ниже операционных системах** и выберите операционные системы, которые могут запускать этот пакет. Нажмите кнопку **Далее**.

13. Откроется страница " **Создание пакета** ". Чтобы изменить пакет, не сохраняя его, установите флажок **продолжить изменение пакета без сохранения с помощью редактора пакетов** . Этот параметр открывает пакет на консоли секвенсор, чтобы можно было изменить пакет перед сохранением. Нажмите кнопку **Далее**.

   Чтобы сохранить пакет немедленно, выберите **сохранить пакет прямо сейчас**. При необходимости добавьте **Описание** , которое будет сопоставлено с пакетом. Описания полезны для идентификации версии и других сведений о пакете.

   **Важно.**  
   Система не поддерживает непечатаемые символы в комментариях и описаниях.



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

**Упорядочение приложения по промежуточного слоя**

1. На компьютере с программой Sequencer выберите **все программы**, а затем — **Виртуализация приложений**Microsoft, а затем выберите **Microsoft Application Virtualization Sequencer**.

2. *<strong><em>В секвенсоре щелкните * </em> создать новый виртуальный пакет приложения </strong> . Выберите команду **создать пакет (по умолчанию)**, а затем нажмите кнопку **Далее**.

3. На странице **Подготовка компьютера** изучите проблемы, которые могут привести к сбою при создании пакета или привести к тому, что пакет может содержать ненужные данные. Прежде чем продолжить, устраните все возможные проблемы. После внесения исправлений нажмите кнопку **Обновить** , чтобы отобразить обновленные сведения. После устранения всех возможных проблем нажмите кнопку **Далее**.

   **Важно.**  
   Если вы хотите отключить антивирусную программу, необходимо сначала проверить компьютер, на котором работает секвенсор App-V 5,0, чтобы убедиться в том, что нежелательные или вредоносные файлы не могут быть добавлены в пакет.



4. На странице **Тип приложения** выберите **промежуточный**по, а затем нажмите кнопку **Далее**.

5. На странице " **Выбор установщика** " нажмите кнопку **Обзор** и укажите файл установки для приложения. Если у приложения нет связанного файла установщика и вы планируете выполнить все инструкции по установке вручную, установите флажок **выбрать этот параметр, чтобы выполнить выборочную установку** , и нажмите кнопку **Далее**.

6. На странице " **имя пакета** " введите имя, которое будет сопоставлено с пакетом. Используйте имя, которое помогает идентифицировать цель и версию приложения, которые будут добавлены в пакет. Имя пакета отобразится в консоли управления App-V 5,0. **Основной каталог виртуальных приложений** отображает путь, по которому будет установлено приложение. Чтобы указать это расположение, введите путь к файлу или нажмите кнопку **Обзор**.

   Нажмите кнопку **Далее**.

7. На странице **установки** , когда программа Sequencer и установщик приложения по промежуточного слоя готовы, вы можете продолжить установку приложения, чтобы секвенсор мог отслеживать процесс установки. Используйте процесс установки приложения для выполнения установки. Если в процессе установки требуется выполнить дополнительные установочные файлы, нажмите кнопку **выполнить**, чтобы найти и запустить дополнительные файлы установки. После завершения установки установите флажок **Установка завершена** , а затем нажмите кнопку **Далее**.

8. На странице **установки** подождите, пока секвенсор настроит пакет виртуальных приложений.

9. На странице **отчета об установке** можно просмотреть сведения о пакете виртуального приложения, который был только что упорядочен. В **дополнительных сведениях**дважды щелкните событие, чтобы получить более подробные сведения. Чтобы продолжить, нажмите кнопку **Далее**.

10. На странице **Целевая операционная** система укажите операционные системы, которые могут запускать этот пакет. Чтобы включить этот пакет для всех поддерживаемых операционных систем в среде, установите флажок **Разрешить выполнение этого пакета для любой операционной системы** . Чтобы настроить запуск этого пакета только в определенных операционных системах, установите флажок **Разрешить запуск этого пакета только на указанных ниже операционных системах** и выберите операционные системы, которые могут запускать этот пакет. Нажмите кнопку **Далее**.

11. Откроется страница **Создание пакета** . Чтобы изменить пакет, не сохраняя его, нажмите кнопку **продолжить, чтобы изменить пакет без сохранения с помощью редактора пакетов**. Этот параметр открывает пакет на консоли секвенсор, чтобы можно было изменить пакет перед сохранением. Нажмите кнопку **Далее**.

    Чтобы сохранить пакет немедленно, выберите **сохранить пакет прямо сейчас**. При необходимости добавьте **Описание** , которое должно быть связано с пакетом. Описания полезны для идентификации версии программы и других сведений о пакете.

    **Важно.**  
    Система не поддерживает непечатаемые символы в комментариях и описаниях.



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

12. Откроется страница **завершения** . При необходимости просмотрите сведения в области **отчета о пакетах виртуальных приложений** и нажмите кнопку **Закрыть**. Эти сведения также доступны в файле **Report.xml** , который находится в каталоге, указанном в действии 11 этой процедуры.

   Пакет теперь доступен в секвенсоре. Чтобы изменить свойства пакета, нажмите **изменить \ [имя пакета \]**.

   **Важно.**  
   После того как вы успешно создадите виртуальный пакет приложения, вы не сможете запустить виртуальный пакет приложения на компьютере, на котором запущен секвенсор.



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## Статьи по теме


[Операции, связанные с администрированием и использованием App-V 5.0](operations-for-app-v-50.md)









