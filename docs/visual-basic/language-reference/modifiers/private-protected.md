---
title: 개인 보호 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a>개인 보호 (Visual Basic)

`Private Protected` 키워드 조합은 멤버 액세스 한정자입니다. A `Private Protected` 멤버는 포함 하는 클래스에서 파생 된 형식에 따라서도 모든 멤버를 포함 하는 클래스에 액세스할 수 있는 경우에 포함 하는 어셈블리가에서 발생 합니다. 

지정할 수 있습니다 `Private Protected` ; 클래스의 멤버에 대해서만 적용할 수 없습니다 `Private Protected` 구조체의 멤버에 게 되므로 구조체를 상속할 수 없습니다.

`Private Protected` 액세스 한정자는 Visual Basic 15.5에서 이상에 지원 됩니다. 를 사용 하려면 Visual Basic 프로젝트 (*.vbproj) 파일에 다음 요소를 추가할 수 있습니다. Visual Basic 15.5 하기만 이상 시스템에 설치 되어, Visual Basic 컴파일러의 최신 버전에서 지 원하는 모든 언어 기능을 활용할 수 있습니다.

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Visual Studio에서에 F1 도움말을 선택 하면 `private protected` 중 하나에 대 한 도움말을 제공 [개인](private.md) 또는 [보호](protected.md)합니다. IDE의 복합 단어 보다는 커서에서 단일 토큰을 선택합니다.

## <a name="rules"></a>규칙

- **선언 컨텍스트입니다.** 사용할 수 있습니다 `Private Protected` 클래스 수준에만 합니다. 즉, 선언 컨텍스트는 `Protected` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.

## <a name="behavior"></a>동작

- **액세스 수준입니다.** 클래스의 모든 코드를 해당 요소에 액세스할 수 있습니다. 모든 기본 클래스에서 파생 되 고 동일한 어셈블리에 포함 된 모든 클래스의 코드에 액세스할 수는 `Private Protected` 기본 클래스의 요소입니다. 그러나 기본 클래스에서 파생 되 고 다른 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스에 액세스할 수 없습니다 `Private Protected` 요소입니다.

- **액세스 한정자입니다.** 액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다. 액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.
  
 `Private Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md) 중첩된 클래스의  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 클래스에서 중첩 대리자  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md) 는 eumeration의 클래스에서 중첩 
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md) 클래스에서 중첩 된 인터페이스의 
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [문을 구조체](../../../visual-basic/language-reference/statements/structure-statement.md) 클래스에서 중첩 된 구조체 
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목

[공용](../../../visual-basic/language-reference/modifiers/public.md)  
[보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
[Friend](friend.md)   
[전용](../../../visual-basic/language-reference/modifiers/private.md)  
[Protected Friend](./protected-friend.md)   
[Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
