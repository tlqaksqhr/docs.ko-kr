---
title: Friend(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df0e8ad1990fe7a1aa495e1794c942813cffb5bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="friend-visual-basic"></a>Friend(Visual Basic)
하나 이상의 선언 된 프로그래밍 요소를 해당 하는 어셈블리 내 에서만 액세스할 수 있도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 대부분의 경우에서 클래스 및 구조체를 선언 하는 구성 요소에서 뿐만 아니라 전체 어셈블리에서 사용할 수 등의 요소를 프로그래밍 하는 것이 좋습니다. 그러나 있습니다 하지 하도록 할 수 (예를 들어 응용 프로그램이 경우 소유) 어셈블리 외부의 코드에서 액세스할 수 있습니다. 이러한 방식으로 요소에 대 한 액세스를 제한 하려는 경우 사용 하 여 선언할 수 있습니다는 `Friend` 한정자입니다.  
  
 다른 클래스, 구조체 및 동일 하 게 컴파일된 모듈의 코드를 모든 어셈블리에 액세스할 수는 `Friend` 해당 어셈블리의 요소입니다.  
  
 `Friend`액세스는 종종 응용 프로그램의 프로그래밍 요소에 대 한 기본 수준 및 `Friend` 는 기본 액세스 인터페이스, 모듈, 클래스 또는 구조체의 수준입니다.  
  
 사용할 수 있습니다 `Friend` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만. 따라서 선언 컨텍스트는 `Friend` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 요소가 있어야 하며 프로시저 수 없습니다.  
  
 사용할 수 있습니다는 `Friend` 와 함께에서 한정자는 [Protected](../../../visual-basic/language-reference/modifiers/protected.md) 같은 선언에는 한정자입니다. 한정자를이 함께 제공 둘 다 `Friend` 액세스 및 자체 클래스에서 및 파생된 클래스에서 동일한 어셈블리의 모든 위치에서 액세스할 수 있도록 선언된 된 요소에 대 한 액세스를 보호 합니다. 지정할 수 있습니다 `Protected Friend` 클래스의 멤버에 대해서만 합니다.  
  
 에 대 한 비교 `Friend` 오류 코드 및 기타 참조, 액세스 한정자 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
> [!NOTE]
>  Friend 어셈블리 모든 형식과로 표시 된 멤버에 액세스할 수 있는 다른 어셈블리 인지를 지정할 수 있습니다 `Friend`합니다. 자세한 내용은 [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)(Friend 어셈블리)를 참조하세요.  
  
## <a name="example"></a>예  
 다음 클래스에서 사용 하는 `Friend` 특정 멤버에 액세스 하는 어셈블리 내 다른 프로그래밍 요소를 허용 하는 한정자입니다.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a>사용법  
 사용할 수는 `Friend` 다음 컨텍스트에서 한정자:  
  
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
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [공용](../../../visual-basic/language-reference/modifiers/public.md)  
 [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
 [전용](../../../visual-basic/language-reference/modifiers/private.md)  
 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
