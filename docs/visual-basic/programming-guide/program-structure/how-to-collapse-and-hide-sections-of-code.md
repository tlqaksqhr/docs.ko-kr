---
title: '방법: 코드 섹션 축소 및 숨기기(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4497c9586182cca9e2be97dc39e5ccb242725d25
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>방법: 코드 섹션 축소 및 숨기기(Visual Basic)
`#Region` 지시문을 사용 하면 Visual Basic 파일에서 코드 섹션 축소 및 숨기기 수 있습니다. `#Region` 지시문을 사용 하면 Visual Studio 코드 편집기를 사용 하는 경우 축소 또는 확장할 수 있는 코드 블록을 지정할 수 있습니다. 선택적으로 코드를 숨기는 기능은 좀 더 관리 및 보다 쉽게 읽을 수 파일을 만듭니다. 자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.  
  
 `#Region` 지시문을 코드 블록의 의미와 같은 지원 `#If...#End If`합니다. 즉, 끝 엔티티; 있으며 한 블록에서 시작할 수 없습니다. 시작 및 종료 같은 블록에 있어야 합니다. `#Region` 지시문 함수 내에서 지원 되지 않습니다.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>축소 하 고 숨기 코드의 섹션  
  
-   사이 코드의 섹션 배치는 `#Region` 및 `#End Region` 다음 예제와 같이 문:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     `#Region` 블록 코드 파일에 여러 번 사용할 수 있습니다; 즉, 사용자가 자신의 프로시저 및 블록을를 차례로 축소할 수 있는 클래스를 정의할 수 있습니다. `#Region` 블록 내의 다른 중첩 될 수도 있습니다 `#Region` 블록입니다.  
  
    > [!NOTE]
    >  코드를 숨기 더라도 컴파일에서 하지 않는 및 영향을 주지 않습니다 `#If...#End If` 문.  
  
## <a name="see-also"></a>참고 항목  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)  
 [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [개요](/visualstudio/ide/outlining)
