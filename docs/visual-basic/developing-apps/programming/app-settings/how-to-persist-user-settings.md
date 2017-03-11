---
title: "How to: Persist User Settings in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings object, persisting user settings"
  - "persistence, persisting user settings [Visual Basic]"
  - "user settings, persisting"
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Persist User Settings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Settings.Save` 메서드를 사용하면 변경 내용을 사용자 설정으로 유지할 수 있습니다.  
  
 일반적으로 응용 프로그램은 종료될 때 변경 내용을 사용자 설정에 유지하도록 설계됩니다.  이것은 몇몇 요인에 따라 설정을 저장하는 데 몇 초의 시간이 걸릴 수 있기 때문입니다.  
  
 자세한 내용은 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)을 참조하십시오.  
  
> [!NOTE]
>  사용자 범위 설정 값은 런타임에 변경하고 저장할 수 있지만, 응용 프로그램 범위 설정은 읽기 전용이므로 프로그래밍 방식으로 변경할 수 없습니다.  응용 프로그램 범위 설정은 **프로젝트 디자이너**를 통해 응용 프로그램을 만들 때 또는 응용 프로그램의 구성 파일을 편집하는 방식으로 변경할 수 있습니다.  자세한 내용은 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)을 참조하십시오.  
  
## 예제  
 이 예제에서는 `LastChanged` 사용자 설정의 값을 변경하고 `My.Settings.Save` 메서드를 호출하여 이 변경 내용을 저장합니다.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/visualbasic/VbVbalrMyResources2/Form1.vb#5)]  
  
 이 예제가 동작하려면 응용 프로그램에 형식이 `Date`인 `LastChanged` 사용자 설정이 있어야 합니다.  자세한 내용은 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)을 참조하십시오.  
  
## 참고 항목  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)