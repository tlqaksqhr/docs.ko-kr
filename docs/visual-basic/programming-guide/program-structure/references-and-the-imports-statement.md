---
title: "References and the Imports Statement (Visual Basic) | Microsoft Docs"
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
  - "assemblies [Visual Basic], namespaces"
  - "references, assembly"
  - "namespaces, assemblies"
  - "referencing assemblies"
  - "Imports statement, referencing assemblies"
  - "assemblies [Visual Basic], references"
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# References and the Imports Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

**프로젝트** 메뉴에서 **참조 추가** 명령을 선택하면 외부 개체를 프로젝트에 사용할 수 있습니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 형식 라이브러리와 유사하지만 더 많은 정보를 포함하는 어셈블리를 참조할 수 있습니다.  
  
## Imports 문  
 어셈블리에는 하나 이상의 네임스페이스가 포함됩니다.  어셈블리에 대한 참조를 추가할 때 모듈 내에서 해당 어셈블리 네임스페이스의 가시성을 제어하는 모듈에 `Imports`문을 추가할 수도 있습니다.  `Imports` 문을 사용하면 고유한 참조를 제공하는 데 필요한 네임스페이스 부분만 사용할 수 있도록 범위 컨텍스트가 제공됩니다.  
  
 `Imports` 문의 구문은 다음과 같습니다.  
  
 `Imports` \[         `|` `Aliasname` \=\] `Namespace`  
  
 `Aliasname`은 가져온 네임스페이스를 참조하기 위해 코드에서 사용할 수 있는 약식 이름을 참조합니다.  `Namespace`는 프로젝트 참조, 프로젝트 내의 정의 또는 이전 `Imports` 문을 통해 사용할 수 있는 네임스페이스입니다.  
  
 모듈에서 `Imports` 문을 횟수에 제한 없이 사용할 수 있습니다.  이렇게 사용된 문은 모든 코드의 앞에 오며, `Option` 문이 있으면 이 문 뒤에 와야 합니다.  
  
> [!NOTE]
>  프로젝트 참조를 `Imports` 문이나 `Declare` 문과 혼동하지 마십시오.  프로젝트 참조는 외부 개체\(예: 어셈블리의 개체\)를 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로젝트에서 사용할 수 있도록 합니다.  `Imports` 문은 프로젝트 참조에 대한 액세스를 단순화하기 위해 사용될 수 있지만 이들 개체에 대한 액세스는 제공하지 않습니다.  `Declare` 문은 동적 연결 라이브러리\(DLL\)에 있는 외부 프로시저에 대한 참조를 선언하는 데 사용합니다.  
  
## Imports 문에서의 별칭 사용  
 `Imports` 문을 사용하면 참조의 정규화된 이름을 명시적으로 입력할 필요가 없기 때문에 클래스의 메서드에 더 쉽게 액세스할 수 있습니다.  별칭을 사용하면 네임스페이스의 한 부분에 보다 익숙한 이름을 할당할 수 있습니다.  예를 들어, 단일 텍스트가 여러 줄에 표시되도록 하는 캐리지 리턴\/줄 바꿈 시퀀스는 <xref:Microsoft.VisualBasic?displayProperty=fullName> 네임스페이스에 있는 <xref:Microsoft.VisualBasic.ControlChars> 모듈의 일부입니다.  이 상수를 별칭 없이 프로그램에서 사용하려면 다음 코드를 입력해야 합니다.  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/references-and-the-impor_1.vb)]  
  
 `Imports` 문은 반드시 모듈의 `Option` 문 바로 다음에 위치해야 합니다.  다음 코드 조각에서는 별칭을 <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName> 모듈로 가져와서 할당하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/references-and-the-impor_2.vb)]  
  
 이렇게 하면 네임스페이스에 대한 참조가 더욱 짧아집니다.  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/references-and-the-impor_3.vb)]  
  
 `Imports` 문에 별칭 이름을 지정하지 않은 경우 가져온 네임스페이스 내에 정의된 요소들을 한정자 없이 모듈에서 사용할 수 있습니다.  그러나 별칭 이름을 지정한 경우에는 이 이름을 해당 네임스페이스 내에 포함된 이름에 대한 한정자로 사용해야 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic>   
 [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: 명령줄을 사용하여 어셈블리 만들기 및 사용](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)