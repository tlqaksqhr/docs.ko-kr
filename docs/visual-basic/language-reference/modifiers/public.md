---
title: Public(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6cd70adf6ec31c56f39d0443d320dd1b00b00d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="public-visual-basic"></a>Public(Visual Basic)
선언 된 프로그래밍 요소를 하나 이상의 액세스 제한이 지정 합니다.  
  
## <a name="remarks"></a>설명  
 구성 요소 또는 클래스 라이브러리와 같은 구성 요소 집합을 게시 하는 경우 일반적으로 프로그래밍 요소 어셈블리와 상호 작용 하는 모든 코드에서 액세스할 수 있도록 합니다. 없이 요소에 대해 무제한 액세스를 하려면 사용 하 여 선언할 수 있습니다 `Public`합니다.  
  
 공용 액세스는 일반 프로그래밍 요소에 대 한 경우이에 대 한 액세스를 제한할 필요가 없습니다. 인터페이스, 모듈, 클래스 또는 구조체 내에 선언 된 액세스 수준 요소에는 기본적으로 `Public` 따로 선언 하지 않습니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 사용할 수 있습니다 `Public` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만. 즉, 선언 컨텍스트는 `Public` 요소 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 이어야 하며 프로시저일 수는 없습니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드가 액세스할 수 있는 해당 `Public` 요소입니다.  
  
-   **기본 액세스 합니다.** 공용 액세스를 프로시저 기본값 내의 지역 변수는에 액세스 한정자를 사용할 수 없습니다.  
  
-   **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다. 액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [전용](../../../visual-basic/language-reference/modifiers/private.md)  
 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
