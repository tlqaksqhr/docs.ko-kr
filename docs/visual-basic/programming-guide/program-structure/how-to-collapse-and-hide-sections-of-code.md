---
title: "방법: (Visual Basic) 코드 섹션 축소 및 숨기기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 200a90b6983277d46b6e5c7b27ee4a90ecf88c40
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>방법: 코드 섹션 축소 및 숨기기(Visual Basic)
`#Region` 지시문을 사용 하면 코드 섹션 축소 및 숨기기 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 파일입니다. `#Region` 지시문을 사용 하면 사용 하는 경우 축소 하거나 확장할 수 있는 코드 블록을 지정할 수는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 코드 편집기입니다. 코드를 선택적으로 숨길 수에 파일 사용 하면 관리 가능 하 고 쉽게 읽을 수 있습니다. 자세한 내용은 참조 [개요](https://docs.microsoft.com/visualstudio/ide/outlining)합니다.  
  
 `#Region`지시문을 코드 블록의 의미와 같은 지원 `#If...#End If`합니다. 즉, 없습니다 한 블록에서 시작과 종료 다른; 시작 및 종료 같은 블록에 있어야 합니다. `#Region`지시문 함수 내에서 지원 되지 않습니다.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>축소 하 고 코드의 섹션을 숨기려면  
  
-   섹션 사이 코드의 배치는 `#Region` 및 `#End Region` 다음 예제와 같이 문:  
  
     [!code-vb[VbVbalrConditionalComp #&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     `#Region` 블록 코드 파일에 여러 번 사용할 수 있습니다; 따라서 사용자 고유의 블록 프로시저 및를 차례로 축소할 수 있는 클래스를 정의할 수 있습니다. `#Region`블록은 다른 내에서 중첩 될 수도 있습니다 `#Region` 블록입니다.  
  
    > [!NOTE]
    >  코드를 숨기 더라도 컴파일에서 하지 않는 및 영향을 주지 않습니다 `#If...#End If` 문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)   
 [#If... ... #Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [개요](https://docs.microsoft.com/visualstudio/ide/outlining)
