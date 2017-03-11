---
title: "Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application object, developing applications"
  - "rapid application development (RAD), My.Application"
  - "rapid application development (RAD), My.Computer"
  - "rapid application development (RAD), My.User"
  - "My.Computer object, developing applications"
  - "My.User object, developing applications"
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

정보 및 일반적으로 사용되는 기능에 대한 액세스를 제공하는 3개의 중심 `My` 개체는 `My.Application` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>\), `My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\) 및 `My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)입니다.  이러한 개체를 사용하여 현재 응용 프로그램, 응용 프로그램이 설치된 컴퓨터 또는 응용 프로그램의 현재 사용자에 관련된 정보에 각각 액세스할 수 있습니다.  
  
## My.Application, My.Computer 및 My.User  
 다음 예제에서는 `My`를 사용하여 정보를 검색하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_2.vb)]  
  
 정보 검색은 물론 이러한 3개의 개체를 통해 노출된 멤버를 사용하면 해당 개체와 관련된 메서드를 실행할 수 있습니다.  예를 들어, 다양한 메서드에 액세스하여 파일을 조작하거나 `My.Computer`를 통해 레지스트리를 업데이트할 수 있습니다.  
  
 파일, 디렉터리 및 드라이브를 조작하는 다양한 메서드와 특성이 포함된 `My`를 사용하면 파일 I\/O가 훨씬 쉽고 빨라집니다.  <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체를 사용하면 구분되거나 너비가 고정된 필드가 있는 구조화된 대용량 파일에서 읽을 수 있습니다.  이 예제에서는 `TextFieldParser` `reader`를 열고 이 개체를 사용하여 `C:\TestFolder1\test1.txt`에서 읽습니다.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_3.vb)]  
  
 `My.Application`을 사용하면 응용 프로그램에 대한 culture를 변경할 수 있습니다.  다음 예제에서는 이 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_4.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [How My Depends on Project Type](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)