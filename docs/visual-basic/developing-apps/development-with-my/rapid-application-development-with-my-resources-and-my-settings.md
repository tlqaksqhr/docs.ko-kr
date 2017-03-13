---
title: "Rapid Application Development with My.Resources and My.Settings (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings object, developing applications"
  - "rapid application development (RAD), My.Resources"
  - "rapid application development (RAD), My.Settings"
  - "My.Resources object, developing applications"
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Rapid Application Development with My.Resources and My.Settings (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Resources` 개체는 응용 프로그램의 리소스에 대한 액세스를 제공하며, 이를 통해 응용 프로그램의 리소스를 동적으로 검색할 수 있습니다.  
  
## 리소스 검색  
 `My.Resources` 개체를 통해 오디오 파일, 아이콘, 이미지, 문자열과 같은 다양한 리소스를 검색할 수 있습니다.  예를 들어, 응용 프로그램의 culture별 리소스 파일에 액세스할 수 있습니다.  다음 예제에서는 폼의 아이콘을 응용 프로그램의 리소스 파일에 저장된 `Form1Icon` 아이콘으로 설정합니다.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources` 개체는 전역 리소스만 노출합니다.  이 개체는 폼과 연관된 리소스 파일에 대한 액세스를 제공하지 않습니다.  폼 리소스에는 폼에서 액세스해야 합니다.  자세한 내용은 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5)를 참조하십시오.  
  
 마찬가지로 `My.Settings` 개체는 응용 프로그램의 설정에 대한 액세스를 제공하며, 이를 통해 응용 프로그램에 대한 속성 설정 및 기타 정보를 동적으로 저장하고 검색할 수 있습니다.  자세한 내용은 [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) 및 [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하십시오.  
  
## 참고 항목  
 [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md)   
 [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Accessing Application Settings](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)