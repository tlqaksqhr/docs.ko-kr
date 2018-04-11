---
title: Private(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a>Private(Visual Basic)
하나 이상의 선언 된 프로그래밍 요소를에서 포함 된 모든 형식을 포함 하 여 해당 변수의 선언 컨텍스트 내 에서만 액세스할 수 있도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 프로그래밍 요소 소유권이 있는 기능 또는 기밀 데이터가 포함 된 경우에 일반적으로 최대한 엄격 하 게 액세스를 제한 합니다. 모듈, 클래스 또는 구조체 정의에 액세스 하는 허용 하 여 최대 한계를 달성 합니다. 이러한 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Private`합니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** `Private`는 모듈 수준에서만 사용할 수 있습니다. 즉, 선언 컨텍스트는 `Private` 요소 모듈, 클래스 또는 구조 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 또는 프로시저일 수 없습니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 선언 컨텍스트 내에서 모든 코드가 액세스할 수 있는 해당 `Private` 요소입니다. 이 코드는 중첩 된 클래스 또는 열거형에 대입 식을 같은 포함 된 형식에 포함 됩니다. 선언 컨텍스트 외부에서 코드에 액세스할 수는 `Private` 요소입니다.  
  
-   **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다. 액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `Private` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
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
 [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
