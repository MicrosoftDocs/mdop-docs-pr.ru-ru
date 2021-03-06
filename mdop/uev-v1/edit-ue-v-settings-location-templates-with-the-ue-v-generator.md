---
title: Изменение шаблонов расположения параметров UE-V с помощью генератора UE-V
description: Изменение шаблонов расположения параметров UE-V с помощью генератора UE-V
author: dansimp
ms.assetid: da78f9c8-1624-4111-8c96-79db7224bd0b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b90cd58761e6ac40c089f3afeade3c445a52ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827112"
---
# Изменение шаблонов расположения параметров UE-V с помощью генератора UE-V


Используйте генератор Microsoft User Experience Virtualization (UE-V) для редактирования шаблонов расположений параметров. Когда измененные параметры добавляются в шаблоны с помощью генератора UE-V, информация о версии в шаблоне автоматически обновляется, чтобы убедиться, что все существующие шаблоны, развернутые в корпоративной среде, обновлены правильно.

**Изменение шаблона расположения параметров UE-V с помощью UE-V Generator**

1.  Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft User Experience Virtualization**и выберите **генератор Microsoft Experience Virtualization**.

2.  Щелкните **изменить шаблон расположения параметров**.

3.  В списке последних использованных шаблонов выберите шаблон, который нужно изменить. Кроме того, можно **Перейти** к файлу шаблона параметров. Чтобы продолжить, нажмите **Далее**.

4.  Проверьте **Свойства**, расположения в **реестре** и расположение **файлов** для шаблона параметров. Внесите необходимые изменения.

    -   Вкладка **Свойства** позволяет просматривать и изменять следующие свойства:

        -   **Имя приложения**: имя приложения, которое написано в описании свойств файла программы.

        -   **Имя программы**: имя программы, которая берется из свойств файла программы. Обычно это имя имеет расширение EXE.

        -   **Версия продукта**: номер версии файла exe приложения. Это свойство вместе с **версией файла**помогает определить, какие приложения предназначены для шаблона расположения параметров. Это свойство принимает основной номер версии. Если это свойство не задано, шаблон расположений параметров будет применяться ко всем версиям продукта.

        -   **Версия файла**: номер версии файла the.exe приложения. Это свойство вместе с **версией продукта**помогает определить, какие приложения предназначены для шаблона расположения параметров. Это свойство принимает основной номер версии. Если это свойство не задано, шаблон расположений параметров будет применяться ко всем версиям программы.

        -   **Имя автора шаблона** (необязательно): имя автора шаблона параметров.

        -   **Электронная почта автора шаблона** (необязательно): адрес электронной почты автора шаблона расположения параметров.

    -   На вкладке " **Реестр** " перечислены разделы **реестра и их** **область** , которые включены в шаблон расположения параметров. Вы можете изменить расположение реестра с помощью раскрывающегося меню **Tasks (задачи** ). Задачи включают в себя добавление новых клавиш, изменение имени или области существующих ключей, удаление разделов и Просмотр реестра, в котором находятся ключи. Когда вы определяете область для реестра, вы можете использовать область " **все параметры** ", чтобы включить все параметры реестра в указанном разделе. Используйте **все параметры** и **подразделы** для включения всех параметров реестра в заданные раздел, подразделы и параметры подраздела.

    -   На вкладке " **файлы** " перечислены путь к файлу и его маска для расположений файлов, включенных в шаблон расположения параметров. Расположение файлов можно изменить с помощью раскрывающегося меню " **задачи** ". Задачи для расположений файлов включают добавление новых файлов и папок, изменение области существующих файлов и папок, удаление файлов и папок, а также открытие выбранного расположения в проводнике Windows. Чтобы включить все файлы в указанную папку, оставьте маску файла пустой.

5.  Нажмите кнопку **сохранить** , чтобы сохранить изменения в шаблоне расположение параметров.

6.  Нажмите кнопку **Закрыть** , чтобы закрыть окно мастера шаблонов параметров. Выйдите из приложения генератора UE-V.

    После изменения шаблона расположения параметров для приложения необходимо протестировать этот шаблон. Разверните пересмотренный шаблон расположений параметров в лабораторной среде, прежде чем переводить его в эксплуатацию на предприятии.

**Редактирование шаблона расположений параметров вручную**

1.  Создайте локальную копию шаблона расположения параметров (XML-файл). UE-V Templates Locations — это XML-файлы, указывающие на расположение, в котором значения параметров в магазине приложений.

2.  Откройте файл шаблона расположения параметров с помощью редактора XML.

3.  Измените файл шаблона расположения параметров. Все изменения должны соответствовать файлу схемы UE-V, определенному в SettingsLocationTempate. xsd. Копия XSD-файла по умолчанию находится в разделе `\ProgramData\Microsoft\UEV\Templates` .

4.  Сохраните файл шаблона расположения параметров и закройте редактор XML.

5.  Проверка измененного файла шаблона расположения параметров с помощью генератора UE-V. Дополнительные сведения о проверке с помощью генератора UE-V можно найти [в разделе Проверка шаблонов расположений параметров ue-v с помощью генератора UE-v](validate-ue-v-settings-location-templates-with-ue-v-generator.md).

## Статьи по теме


[Работа с пользовательскими шаблонами UE-V и генератором UE-V](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[Операции в UE-V 1.0](operations-for-ue-v-10.md)

 

 





