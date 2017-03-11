---
title: "/imports (Visual Basic) | Microsoft Docs"
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
  - "/imports compiler option [Visual Basic]"
  - "imports compiler option [Visual Basic]"
  - "-imports compiler option [Visual Basic]"
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /imports (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정한 어셈블리에서 네임스페이스를 가져옵니다.  
  
## 구문  
  
```  
/imports:namespaceList  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`namespaceList`|필수 요소.  가져올 네임스페이스를 쉼표로 구분한 목록입니다.|  
  
## 설명  
 `/imports` 옵션은 현재 소스 파일 집합에 정의되어 있거나 참조된 어셈블리에 있는 모든 네임스페이스를 가져옵니다.  
  
 `/imports`로 지정된 네임스페이스의 멤버는 컴파일의 모든 소스 코드 파일에 사용할 수 있습니다.  [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 사용하여 하나의 소스 코드 파일에서 네임스페이스를 사용할 수 있습니다.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/imports를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **참조** 탭을 클릭합니다.<br />3.  **사용자 가져오기 추가** 단추 옆의 상자에 네임스페이스 이름을 입력합니다.<br />4.  **사용자 가져오기 추가** 단추를 클릭합니다.|  
  
## 예제  
 다음 코드는 `/imports:system`이 지정된 경우에 컴파일됩니다.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/imports_1.vb)]  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)