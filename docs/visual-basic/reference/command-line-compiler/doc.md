---
title: "/doc | Microsoft Docs"
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
  - "doc compiler option [Visual Basic]"
  - "-doc compiler option [Visual Basic]"
  - "/doc compiler option [Visual Basic]"
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /doc
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

XML 파일에 대해 문서 주석을 처리합니다.  
  
## 구문  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`+`  &#124; `-`|선택적 요소.  \+를 지정하거나 `/doc`만 지정하면 컴파일러가 문서 정보를 생성하여 XML 파일에 저장합니다.  `-` 를 지정하는 것은 `/doc`를 지정하지 않는 것과 동일하므로 문서 정보가 생성되지 않습니다.|  
|`file`|`/doc:`을 사용하는 경우 필수적 요소입니다.  컴파일 소스 코드 파일의 주석으로 채워지는 출력 XML 파일을 지정합니다.  파일 이름에 공백이 포함되어 있는 경우 이름을 따옴표\(" "\)로 묶습니다.|  
  
## 설명  
 `/doc` 옵션은 컴파일러에서 문서 주석을 포함하는 XML 파일을 생성하는지 여부를 제어합니다.  `/doc:``file` 구문을 사용하는 경우 `file` 매개 변수는 XML 파일의 이름을 지정합니다.  `/doc` 또는 `/doc+`를 사용하는 경우 컴파일러에서는 작성 중인 실행 파일이나 라이브러리에서 XML 파일 이름을 가져옵니다.  `/doc-`를 사용하거나 `/doc` 옵션을 지정하지 않는 경우 컴파일러에서는 XML 파일을 만들지 않습니다.  
  
 소스 코드 파일에서 문서 주석은 다음 정의 앞에 올 수 있습니다.  
  
-   사용자 정의 형식\(예: [클래스](../../../visual-basic/language-reference/statements/class-statement.md) 또는 [인터페이스](../../../visual-basic/language-reference/statements/interface-statement.md)\)  
  
-   멤버\(예: 필드, [이벤트](../../../visual-basic/language-reference/statements/event-statement.md), [속성](../../../visual-basic/language-reference/statements/property-statement.md), [함수](../../../visual-basic/language-reference/statements/function-statement.md) 또는 [서브루틴](../../../visual-basic/language-reference/statements/sub-statement.md)\)  
  
 생성된 XML 파일을 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] [IntelliSense](/visual-studio/ide/using-intellisense) 기능과 함께 사용하려면 XML 파일의 이름을 지원하려는 어셈블리의 이름과 동일하게 지정합니다.  어셈블리가 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] 프로젝트에서 참조될 때 .xml 파일도 함께 검색되도록 XML 파일을 어셈블리와 같은 디렉터리에 둡니다.  IntelliSense가 프로젝트 내부나 프로젝트에서 참조하는 프로젝트 내부의 코드에 대해 작동하는 데 XML 문서 파일이 반드시 필요한 것은 아닙니다.  
  
 `/target:module`로 컴파일하지 않는 한 XML 파일에는 `<assembly></assembly>` 태그가 포함됩니다.  이러한 태그는 컴파일 출력 파일에 대한 어셈블리 매니페스트를 포함하는 파일의 이름을 지정합니다.  
  
 코드의 주석으로 문서를 생성하는 방법은 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)를 참조하십시오.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/doc를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **XML 문서 파일 생성** 상자에서 값을 설정합니다.|  
  
## 예제  
 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)에서 예제를 참조하십시오.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)