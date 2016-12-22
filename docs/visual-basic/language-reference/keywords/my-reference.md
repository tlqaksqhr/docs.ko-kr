---
title: "My Reference (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My feature"
  - "My reference"
ms.assetid: 6f803bd7-21ff-4569-b1fe-b00a6678b1e3
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# My Reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`My` 기능을 사용하면 일반적으로 사용하는 메서드, 속성 및 이벤트에 쉽게 액세스하여 보다 빠르고 편리한 프로그래밍을 할 수 있습니다.  다음 표에서는 `My`에 포함되어 있는 개체와 각 개체로 수행할 수 있는 작업을 보여 줍니다.  
  
|**동작**|**개체**|  
|------------|------------|  
|응용 프로그램 정보 및 서비스 액세스|`My.Application` 개체는 다음 클래스로 구성됩니다.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>는 모든 프로젝트에서 사용할 수 있는 멤버를 제공합니다.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 메서드는 Windows Forms 응용 프로그램에서 사용할 수 있는 멤버를 제공합니다.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> 메서드는 콘솔 응용 프로그램에서 사용할 수 있는 멤버를 제공합니다.|  
|호스트 컴퓨터와 해당 리소스, 서비스 및 데이터 액세스|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|  
|현재 프로젝트의 폼 액세스|[My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|응용 프로그램 로그 액세스|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|  
|현재 웹 요청 액세스|[My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)|  
|리소스 요소 액세스|[My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md)|  
|현재 웹 응답 액세스|[My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)|  
|사용자 및 응용 프로그램 수준 설정 액세스|[My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md)|  
|현재 사용자의 보안 컨텍스트 액세스|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|  
|현재 프로젝트에서 참조하는 XML Web services 액세스|[My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
  
## 참고 항목  
 [Overview of the Visual Basic Application Model](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)   
 [Development with My](../../../visual-basic/reference/command-line-compiler/index.md)