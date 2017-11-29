---
title: "My.Application, My.Computer 및 My.User를 사용한 작업 수행(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d55e0b3a126f2216d005c7bddbcaefb7d8f0a580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>My.Application, My.Computer 및 My.User를 사용한 작업 수행(Visual Basic)
세 개의 핵심 `My` 액세스 정보 및 일반적으로 사용 되는 기능을 제공 하는 개체는 `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), 및 `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). 현재 응용 프로그램, 응용 프로그램은 설치 하는 컴퓨터 또는 응용 프로그램의 현재 사용자와 관련 된 정보를 각각 액세스할 수 이러한 개체를 사용할 수 있습니다.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer 및 My.User  
 다음 예에서는 정보 수 있는 방법을 보여 줍니다. 사용 하 여 검색할 `My`합니다.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 정보를 검색 하는 것 외에도 이러한 세 가지 개체를 통해 노출 되는 멤버 수 있습니다 해당 개체와 관련 된 메서드를 실행 합니다. 예를 들어, 다양 한 파일을 조작 하거나 통해 레지스트리를 업데이트할 방법 액세스할 수 있습니다 `My.Computer`합니다.  
  
 파일 I/O가 훨씬 쉽고 빠르게 `My`, 다양 한 파일, 디렉터리 및 드라이브를 조작 하기 위한 메서드와 속성을 포함 하는 합니다. <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체 고정 폭 필드 또는 구분 큰 구조화 된 파일에서 읽을 수 있습니다. 이 예제는 `TextFieldParser``reader` 에서 읽기를 사용 하 여 `C:\TestFolder1\test1.txt`합니다.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application`응용 프로그램에 대 한 문화권을 변경할 수 있습니다. 다음 예제에서는이 메서드를 호출 수 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [My가 프로젝트 형식에 의존하는 방식](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
