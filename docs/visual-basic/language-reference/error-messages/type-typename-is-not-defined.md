---
title: "Type &#39;&lt;typename&gt;&#39; is not defined | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30002"
  - "bc30002"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30002"
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Type &#39;&lt;typename&gt;&#39; is not defined
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문에서 정의되지 않은 형식을 참조했습니다.  선언문에는 `Enum`, `Structure`, `Class` 또는 `Interface`와 같은 형식을 정의할 수 있습니다.  
  
 **오류 ID:** BC30002  
  
### 이 오류를 해결하려면  
  
-   형식 정의와 해당 참조의 철자가 동일한지 확인합니다.  
  
-   참조가 형식 정의에 액세스할 수 있는지 확인합니다.  예를 들어, 형식이 다른 모듈에서 `Private`으로 선언되었으면 참조하는 모듈로 형식 정의를 옮기거나 `Public`으로 선언합니다.  
  
-   형식의 네임스페이스가 프로젝트 내에서 다시 정의되지 않는지 확인합니다.  다시 정의되는 경우 `Global` 키워드를 사용하여 형식 이름을 정규화합니다.  예를 들어 프로젝트에서 `System`이라는 네임스페이스를 정의하는 경우 `Global.System.Object`와 같이 `Global` 키워드로 정규화해야 <xref:System.Object?displayProperty=fullName> 형식에 액세스할 수 있습니다.  
  
-   형식이 정의되었으나 형식이 정의된 개체 라이브러리나 형식 라이브러리가 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에 등록되지 않은 경우 **프로젝트** 메뉴에서 **참조 추가**를 클릭한 다음 알맞은 개체 라이브러리나 형식 라이브러리를 선택합니다.  
  
-   형식이 대상 .NET Framework 프로필의 일부인 어셈블리에 있는지 확인합니다.  자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](/visual-studio/msbuild/troubleshooting-dotnet-framework-targeting-errors)을 참조하십시오.  
  
## 참고 항목  
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)