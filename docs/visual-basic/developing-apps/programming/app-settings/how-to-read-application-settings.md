---
title: "How to: Read Application Settings in Visual Basic | Microsoft Docs"
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
  - "reading application settings"
  - "My.Settings object, reading application settings"
  - "application settings, reading"
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# How to: Read Application Settings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Settings` 개체에서 설정의 속성에 액세스하여 사용자 설정을 읽을 수 있습니다.  
  
 `My.Settings` 개체는 각 설정을 속성으로 노출합니다.  속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다.  설정의 **범위**는 속성이 읽기 전용인지 여부를 나타냅니다. **응용 프로그램** 범위 설정의 속성은 읽기 전용인 반면 **사용자** 범위 설정의 속성은 읽기\/쓰기입니다.  자세한 내용은 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)을 참조하십시오.  
  
## 예제  
 이 예제에서는 `Nickname` 설정의 값을 표시합니다.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 이 예제가 동작하려면 응용 프로그램에 형식이 `String`인 `Nickname` 설정이 있어야 합니다.  자세한 내용은 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)을 참조하십시오.  
  
## 참고 항목  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)