---
title: "Module 문"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92cdcd1919f21243118108da3bc382ea5d954130
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="module-statement"></a>Module 문
모듈의 이름을 선언 하 고 변수, 속성, 이벤트 및 모듈을 구성 하는 프로시저의 정의 소개 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.  
  
 `accessmodifier`  
 선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
-   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `name`  
 필수 요소. 이 모듈의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
 `statements`  
 선택 사항입니다. 변수, 속성, 이벤트, 프로시저 및이 모듈의 중첩된 형식을 정의 하는 문입니다.  
  
 `End Module`  
 종료는 `Module` 정의 합니다.  
  
## <a name="remarks"></a>설명  
 A `Module` 문은 해당 네임 스페이스에서 사용할 수 있는 참조 형식을 정의 합니다. A *모듈* (라고도 *기본 모듈*)와 유사 하지만 몇 가지 중요 한 차이가 클래스에 있습니다. 모든 모듈 인스턴스 중 하나만 있으며 만들거나 변수에 할당할 필요가 없습니다. 모듈 상속을 지원 하지 않거나 인터페이스를 구현 합니다. 모듈은 공지는 *형식* 의미는 클래스 또는 구조체에서-모듈의 데이터 형식을 갖도록 프로그래밍 요소를 선언할 수 없습니다.  
  
 사용할 수 있습니다 `Module` 네임 스페이스 수준 에서만. 즉,는 *선언 컨텍스트* 모듈 소스 파일 또는 네임 스페이스, 이어야 하며 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다. 모든 형식 또는 다른 모듈에서 모듈을 중첩할 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 모듈은 프로그램으로 수명이 동일 합니다. 멤버는 모든 `Shared`, 이들 또한 수명이 같은 프로그램의 것입니다.  
  
 모듈은 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다. 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 모듈의 모든 멤버는 암시적 `Shared`합니다.  
  
## <a name="classes-and-modules"></a>클래스와 모듈  
 이 요소는 많은 공통점이 있지만 중요 한 차이가 있습니다.  
  
-   **용어입니다.** 이전 버전의 Visual Basic 모듈의 두 가지 유형의 인식: *클래스 모듈* (.cls 파일) 및 *표준 모듈* (.bas 파일). 현재 버전에서는 이러한 *클래스* 및 *모듈*각각.  
  
-   **공유 멤버입니다.** 클래스의 멤버는 공유 인지 또는 인스턴스 멤버를 제어할 수 있습니다.  
  
-   **개체 방향입니다.** 클래스는 개체 지향적 있지만 모듈이 없습니다. 따라서 클래스만 개체로 인스턴스화할 수 있습니다. 자세한 내용은 참조 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **한정자입니다.** 모든 모듈 멤버는 암시적 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)합니다. 사용할 수 없습니다는 `Shared` 키워드를 선언 하는 멤버를 모든 멤버의 공유 상태를 변경할 수 없습니다.  
  
-   **상속.** 모듈 이외의 다른 모든 형식에서 상속할 수 없습니다 <xref:System.Object>, 되는 모든 모듈에서 상속 합니다. 특히, 하나의 모듈에서 다른 상속할 수 없습니다.  
  
     사용할 수 없습니다는 [Inherits 문은](../../../visual-basic/language-reference/statements/inherits-statement.md) 모듈 정의에 포함 하 여 지정 하려면 <xref:System.Object>합니다.  
  
-   **기본 속성입니다.** 모듈의 기본 속성을 정의할 수 없습니다. 자세한 내용은 참조 [기본](../../../visual-basic/language-reference/modifiers/default.md)합니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 모듈 내에서 액세스 수준으로 각 멤버를 선언할 수 있습니다. 모듈 멤버는 기본적으로 [공용](../../../visual-basic/language-reference/modifiers/public.md) 변수와 상수를 제외 하 고는 기본적으로 액세스 [개인](../../../visual-basic/language-reference/modifiers/private.md) 액세스 합니다. 모듈에 보다 제한적인 해당 멤버 중 하나를 지정 된 모듈의 액세스 수준을 우선적으로 적용 합니다.  
  
-   **범위입니다.** 모듈은 해당 네임 스페이스에서 범위에 있습니다.  
  
     모든 모듈 멤버의 범위는 전체 모듈입니다. 모든 멤버를 진행 하는 *형식 승격*, 모듈을 포함 하는 네임 스페이스 수준을 올릴 수의 범위에 이르게 됩니다. 자세한 내용은 참조 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)합니다.  
  
-   **검증 합니다.** 여러 모듈 프로젝트에 있고 두 개 이상의 모듈에서 동일한 이름 가진 멤버를 선언할 수 있습니다. 그러나 모듈 외부에서 참조 되는 경우 적절 한 모듈 이름으로 이러한 멤버에 대 한 참조를 정규화 해야 합니다. 자세한 내용은 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
