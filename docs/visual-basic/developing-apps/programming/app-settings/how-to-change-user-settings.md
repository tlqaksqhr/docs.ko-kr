---
title: "How to: Change User Settings in Visual Basic | Microsoft Docs"
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
  - "user settings, changing in Visual Basic"
  - "user settings"
  - "My.Settings object, changing user settings"
  - "examples [Visual Basic], changing user settings"
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Change User Settings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Settings` 개체의 설정 속성에 새 값을 할당하여 사용자 설정을 변경할 수 있습니다.  
  
 `My.Settings` 개체는 각 설정을 속성으로 노출합니다.  속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다.  설정의 **범위**에 따라 속성이 읽기 전용인지 여부가 결정됩니다. **응용 프로그램** 범위 설정의 속성은 읽기 전용인 반면 **사용자** 범위 설정의 속성은 읽기\/쓰기입니다.  자세한 내용은 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)을 참조하십시오.  
  
> [!NOTE]
>  사용자 범위 설정 값은 런타임에 변경하고 저장할 수 있지만, 응용 프로그램 범위 설정은 읽기 전용이므로 프로그래밍 방식으로 변경할 수 없습니다.  응용 프로그램 범위 설정은 응용 프로그램의 구성 파일을 편집하거나 **프로젝트 디자이너**를 사용하여 응용 프로그램을 만들 때 변경할 수 있습니다.  자세한 내용은 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)을 참조하십시오.  
  
## 예제  
 이 예제에서는 `Nickname` 사용자 설정의 값을 변경합니다.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 이 예제가 동작하려면 응용 프로그램에 형식이 `String`인 `Nickname` 사용자 설정이 있어야 합니다.  
  
 응용 프로그램은 응용 프로그램이 종료될 때 사용자 설정을 저장합니다.  설정을 즉시 저장하려면 `My.Settings.Save` 메서드를 호출합니다.  자세한 내용은 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)을 참조하십시오.  
  
## 참고 항목  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [How to: Create Property Grids for User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)