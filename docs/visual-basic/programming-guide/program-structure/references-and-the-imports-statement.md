---
title: "참조 및 Imports 문 (Visual Basic) | Microsoft 문서"
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
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
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
ms.openlocfilehash: 283a27e7703b31a9aeed8f7e4104e89b7ff78525
ms.lasthandoff: 03/13/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a>참조 및 Imports 문(Visual Basic)
사용할 수 있습니다 외부 개체를 프로젝트를 선택 하 여는 **참조 추가** 명령에 **프로젝트** 메뉴. 참조에 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 같은 형식 라이브러리 하지만 자세한 정보를 포함 하는 어셈블리를 가리킬 수 있습니다.  
  
## <a name="the-imports-statement"></a>Imports 문  
 하나 이상의 네임 스페이스를 포함 하는 어셈블리입니다. 어셈블리에 대 한 참조를 추가할 때 추가할 수도 있습니다는 `Imports` 모듈 내에서 해당 어셈블리의 네임 스페이스의 가시성을 제어 하는 모듈에는 문입니다. `Imports` 문은 고유한 참조를 제공 하는 데 필요한 네임 스페이스의 부분에만 사용할 수 있도록 범위 컨텍스트가 제공 합니다.  
  
 `Imports` 문에 다음 구문:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname`가져온된 네임 스페이스를 참조 하도록 코드 내에서 사용할 수는 짧은 이름으로 참조 합니다. `Namespace`네임 스페이스를 통해 사용할 수 있는 프로젝트 참조를 프로젝트 내에서 정의 통해 또는 이전은 `Imports` 문입니다.  
  
 모듈에는 개수에 제한 없이 포함 될 수 있습니다 `Imports` 문입니다. 후 나타나야 `Option` 문, 있는 경우 다른 코드 전에 합니다.  
  
> [!NOTE]
>  프로젝트 참조를 혼동 하지 마십시오는 `Imports` 문 또는 `Declare` 문입니다. 프로젝트 참조 어셈블리의 개체와 같은 외부 개체를 사용할 수 있도록 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트입니다. `Imports` 문을 프로젝트 참조에 대 한 액세스를 간소화 하 고 있지만 이러한 개체에 대 한 액세스를 제공 하지 않습니다. `Declare` 문을 사용 하는 외부 프로시저 동적 연결 라이브러리 (DLL)에 대 한 참조를 선언 합니다.  
  
## <a name="using-aliases-with-the-imports-statement"></a>Imports 문을 사용 하 여 별칭을 사용 하 여  
 `Imports` 문을 사용 하면 클래스의 메서드에 액세스할 쉽게 명시적으로 참조의 정규화 된 이름을 입력할 필요가 없습니다. 별칭을 통해 네임 스페이스의 한 부분에 친숙 한 이름을 할당할 수 있습니다. 예를 들어, 캐리지 리턴/줄 바꿈 시퀀스는 단일 여러 줄에 표시할 텍스트를 일부인는 <xref:Microsoft.VisualBasic.ControlChars>모듈에는 <xref:Microsoft.VisualBasic?displayProperty=fullName>네임 스페이스.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars> 이 상수 별칭 없이 프로그램을 사용 하려면 다음 코드를 입력 해야 합니다.  
  
 [!code-vb[VbVbalrApplication #&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`문은 바로 다음 첫 번째 줄은 반드시 `Option` 모듈의 문이 있습니다. 다음 코드 조각에는 가져오기에 대 한 별칭을 할당 하는 방법을 보여 줍니다는 <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>모듈:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>  
  
 [!code-vb[VbVbalrApplication #&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 이 네임 스페이스에 대 한 향후 참조 상당히 단축 될 수 있습니다.  
  
 [!code-vb[VbVbalrApplication #&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 하는 경우는 `Imports` 문에 별칭 이름을 지정 하지 않은, 한정자 없이 모듈에는 가져온된 네임 스페이스 내에 정의 된 요소를 사용할 수 있습니다. 별칭 이름을 지정 됩니다 해당 네임 스페이스 내에 포함 된 이름에 대 한 한정자로 사용 되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic>   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [방법: 명령줄을 사용 하 여 어셈블리 만들기 및 사용](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
