---
title: "Accessing Application Forms (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "forms, communicating between"
  - "application forms, accessing"
  - "forms, accessing one from another"
  - "My.Forms object"
  - "forms, accessing all open"
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Accessing Application Forms (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Forms` 개체를 사용하면 응용 프로그램의 프로젝트에 선언된 각 Windows Form의 인스턴스에 쉽게 액세스할 수 있습니다.  또한 `My.Application` 개체의 속성을 사용하여 응용 프로그램의 시작 화면과 기본 폼에 액세스하고 응용 프로그램의 열려 있는 폼 목록을 가져올 수 있습니다.  
  
## 작업  
 다음 표에서는 응용 프로그램의 폼에 액세스하는 방법을 보여 주는 예제를 나열합니다.  
  
|||  
|-|-|  
|To|참조|  
|응용 프로그램의 한 폼에서 다른 폼에 액세스합니다.|[My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|응용 프로그램에서 열려 있는 모든 폼의 제목을 표시합니다.|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|응용 프로그램이 시작될 때 시작 화면을 상태 정보로 업데이트합니다.|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)