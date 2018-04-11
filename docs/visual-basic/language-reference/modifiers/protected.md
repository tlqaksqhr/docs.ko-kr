---
title: Protected(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a>Protected(Visual Basic)
하나 이상의 선언 된 프로그래밍 요소는 자체 클래스 내부나 파생 클래스에서 에서만 액세스할 수를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 클래스에서 선언 된 프로그래밍 요소 중요 한 데이터 나 제한 된 코드를 포함 하는 경우에 따라 및 요소에 대 한 액세스를 제한 하려는 경우. 그러나 클래스는 상속 될 수 없습니다 파생된 클래스의 계층 구조를 예상 하는 경우 데이터 나 코드에 액세스 하려면 해당 파생된 클래스에 대 한 할 수 있습니다. 이 경우 요소는 기본 클래스에서 및 모든 파생된 클래스에서 액세스할 수 있도록 합니다. 이런이 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Protected`합니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 사용할 수 있습니다 `Protected` 클래스 수준에만 합니다. 즉, 선언 컨텍스트는 `Protected` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.  
  
-   **결합 된 한정자입니다.** 사용할 수 있습니다는 `Protected` 와 함께 한정자는 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 같은 선언에는 한정자입니다. 이렇게 하면 선언 된 요소 자체 클래스에서 및 파생된 클래스에서 동일한 어셈블리의 모든 위치에서 액세스할 수 있습니다. 지정할 수 있습니다 `Protected Friend` 클래스의 멤버에 대해서만 합니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 클래스의 모든 코드를 해당 요소에 액세스할 수 있습니다. 모든 기본 클래스에서 파생 된 모든 클래스의 코드에 액세스할 수는 `Protected` 기본 클래스의 요소입니다. 이 파생의 모든 세대에 대해 true입니다. 즉, 클래스에 액세스할 수 있도록 `Protected` 기본 클래스 및 등의 기본 클래스의 요소입니다.  
  
     보호 된 액세스는 상위 또는 하위 집합의 friend 액세스 하지 않습니다.  
  
-   **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다. 액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [공용](../../../visual-basic/language-reference/modifiers/public.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [전용](../../../visual-basic/language-reference/modifiers/private.md)  
 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
