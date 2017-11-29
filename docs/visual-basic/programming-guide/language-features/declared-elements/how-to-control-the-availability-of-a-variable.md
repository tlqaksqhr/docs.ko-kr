---
title: "방법: 변수의 사용 가능성 제어(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 004fb101661fadeaee084e1f9374ca8332ac7234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>방법: 변수의 사용 가능성 제어(Visual Basic)
지정 하 여 변수의 사용 가능성 제어 해당 *액세스 수준*합니다. 액세스 수준 변수에 쓰거나 읽을 수 있는 코드를 결정 합니다.  
  
-   *멤버 변수* (프로시저 외부 및 모듈 수준에서 정의 됨) 기본적으로 공용 액세스를 확인 하는 모든 코드에 액세스할 수 있습니다. 액세스 한정자를 지정 하 여이 변경할 수 있습니다.  
  
-   *지역 변수* (프로시저 내에 정의 된)가 프로시저 내의 코드만 액세스할 수 있지만 공용 액세스 명목상으로 있어야 합니다. 지역 변수 형식의 액세스 수준을 변경할 수 없습니다 하지만 포함 된 프로시저의 액세스 수준을 변경할 수 있습니다.  
  
 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="private-and-public-access"></a>개인 및 공용 액세스  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>변수를 해당 모듈, 클래스 또는 구조체 내 에서만 액세스할 수 있도록 하려면  
  
1.  위치는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 프로시저 외부에 모듈, 클래스 또는 구조체 내에서 변수에 대 한 합니다.  
  
2.  포함는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드는 `Dim` 문.  
  
     읽거나에서 아니라 하지만 모듈, 클래스 또는 구조체 내에서 변수를 쓸 수 밖에 있습니다.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>변수를 볼 수 있는 모든 코드에서 액세스할 수 있도록 하려면  
  
1.  멤버 변수를 배치에서 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.  
  
2.  포함는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 키워드는 `Dim` 문.  
  
     읽기 또는 어셈블리와 함께 상호 작용 하는 모든 코드에서 변수에 쓰기 수 있습니다.  
  
 또는  
  
1.  지역 변수를 배치에서 `Dim` 프로시저 내의 변수에 대 한 문을 합니다.  
  
2.  포함 되지 않습니다는 `Public` 키워드는 `Dim` 문.  
  
     읽거나에서 변수는 프로시저에서 아무 곳 이나 하지만에서 아니라에 쓸 수 밖에 있습니다.  
  
## <a name="protected-and-friend-access"></a>보호 및 Friend 액세스  
 변수는 해당 클래스 및 모든 파생된 클래스 또는 어셈블리의 액세스 수준을 제한할 수 있습니다. 파생된 클래스에서 또는 동일한 어셈블리의 다른 위치에 코드에서 액세스할 수 있는 이러한 제한의 합집합을 지정할 수도 있습니다. 결합 하 여이 합집합을 지정 된 `Protected` 및 `Friend` 동일한 선언에서 키워드입니다.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>변수는 해당 클래스와 모든 파생된 클래스 내 에서만 액세스할 수 있도록 하려면  
  
1.  위치는 `Dim` 프로시저 외부 클래스 내에서 변수에 대 한 문을 합니다.  
  
2.  포함는 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) 키워드는 `Dim` 문.  
  
     읽거나,에서 파생 된 클래스 내에서 뿐 아니라 해당 클래스에서 변수를 쓸 수 파생 체인의 모든 클래스 외부입니다.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>변수를 동일한 어셈블리 내 에서만 액세스할 수 있도록 하려면  
  
1.  위치는 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.  
  
2.  포함는 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 키워드는 `Dim` 문.  
  
     읽거나에서 아니라 있지만 동일한 어셈블리에 있는 모든 코드에서 뿐만 아니라 모듈, 클래스 또는 구조체 내에서 변수를 쓸 수 어셈블리 외부에 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용한 변수 선언을 `Public`, `Protected`, `Friend`, `Protected Friend`, 및 `Private` 액세스 수준을 합니다. 경우는 `Dim` 문에서 액세스 수준을 포함할 필요가 없습니다는 `Dim` 키워드입니다.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 더 제한적인 변수를 액세스 수준에 악성 코드가 부적절 하 게 가능성이 줄어듭니다 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [공용](../../../../visual-basic/language-reference/modifiers/public.md)  
 [보호됨](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [전용](../../../../visual-basic/language-reference/modifiers/private.md)
