---
title: 선언 컨텍스트 및 기본 액세스 수준(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: b30b1068fe662d5f0318a1712dc4690b79bd739d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605448"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>선언 컨텍스트 및 기본 액세스 수준(Visual Basic)
이 항목에서는 있는 Visual Basic 형식과 다른 형식 내에서 선언 될 수 있으며 어떤 액세스 수준을 기본적으로 지정 하지 않은 경우를 설명 합니다.  
  
## <a name="declaration-context-levels"></a>선언 컨텍스트 수준  
 *선언 컨텍스트* 프로그래밍 요소의 선언 되는 코드의 영역입니다. 이 종종 라고도 하는 다른 프로그래밍 요소는 *요소를 포함 하*합니다.  
  
 수준을 선언 컨텍스트는 다음과 같습니다.  
  
-   *Namespace 수준* -클래스, 구조체, 모듈 또는 인터페이스를 제외한 소스 파일이 나 네임 스페이스 내  
  
-   *모듈 수준* — 블록 또는 프로시저일 내부가 아니라 클래스, 구조체, 모듈 또는 인터페이스 내에서  
  
-   *프로시저 수준* -프로시저 또는 블록 내에서 (예: `If` 또는 `For`)  
  
 다음 표에서 해당 선언 컨텍스트에 따라 다양 한 선언 된 프로그래밍 요소에 대 한 기본 액세스 수준을 보여 줍니다.  
  
|선언 요소|Namespace 수준|모듈 수준|프로시저 수준|  
|----------------------|---------------------|------------------|---------------------|  
|변수 ([Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md))|허용 되지 않습니다.|`Private` (`Public` 에 `Structure`에서 허용 되지 않음, `Interface`)|`Public`|  
|상수 ([Const 문](../../../visual-basic/language-reference/statements/const-statement.md))|허용 되지 않습니다.|`Private` (`Public` 에 `Structure`에서 허용 되지 않음, `Interface`)|`Public`|  
|열거형 ([Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|허용 되지 않습니다.|  
|클래스 ([Class 문](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|허용 되지 않습니다.|  
|구조 ([문을 구조체](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|허용 되지 않습니다.|  
|모듈 ([Module 문](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|허용 되지 않습니다.|허용 되지 않습니다.|  
|인터페이스 ([Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|허용 되지 않습니다.|  
|프로시저 ([문을 작동](../../../visual-basic/language-reference/statements/function-statement.md), [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md))|허용 되지 않습니다.|`Public`|허용 되지 않습니다.|  
|외부 참조 ([선언 문의](../../../visual-basic/language-reference/statements/declare-statement.md))|허용 되지 않습니다.|`Public` (에 사용할 수 없습니다 `Interface`)|허용 되지 않습니다.|  
|연산자 ([Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md))|허용 되지 않습니다.|`Public` (에 사용할 수 없습니다 `Interface` 또는 `Module`)|허용 되지 않습니다.|  
|속성 ([Property 문](../../../visual-basic/language-reference/statements/property-statement.md))|허용 되지 않습니다.|`Public`|허용 되지 않습니다.|  
|기본 속성 ([기본](../../../visual-basic/language-reference/modifiers/default.md))|허용 되지 않습니다.|`Public` (에 사용할 수 없습니다 `Module`)|허용 되지 않습니다.|  
|이벤트 ([Event 문](../../../visual-basic/language-reference/statements/event-statement.md))|허용 되지 않습니다.|`Public`|허용 되지 않습니다.|  
|대리자 ([Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|허용 되지 않습니다.|  
  
 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [전용](../../../visual-basic/language-reference/modifiers/private.md)  
 [공용](../../../visual-basic/language-reference/modifiers/public.md)
