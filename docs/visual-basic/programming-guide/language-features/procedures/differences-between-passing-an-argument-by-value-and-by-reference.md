---
title: 인수를 값으로 전달할 때와 참조로 전달할 때의 차이점(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 4e846c59d3da01d4d9fe943795376c37db4fb397
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>인수를 값으로 전달할 때와 참조로 전달할 때의 차이점(Visual Basic)
프로시저에 하나 이상의 인수를 전달 하는 경우 각 인수에서 호출 코드의 기본 프로그래밍 요소에 해당 합니다. 이 내부 요소 값 또는 그에 대 한 참조를 전달할 수 있습니다. 이것은 *전달 메커니즘*합니다.  
  
## <a name="passing-by-value"></a>값으로 전달  
 인수를 전달 하면 *값별로* 지정 하 여는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 프로시저 정의에서 해당 매개 변수에 대 한 키워드입니다. 이 전달 메커니즘을 사용 하는 경우 Visual Basic 프로시저의 지역 변수에는 기본 프로그래밍 요소의 값을 복사 합니다. 호출 코드의 프로시저 코드 내부 요소에 대 한 액세스를 않아도 됩니다.  
  
## <a name="passing-by-reference"></a>참조로 전달  
 인수를 전달 하면 *참조로* 지정 하 여는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 프로시저 정의에서 해당 매개 변수에 대 한 키워드입니다. 이 전달 메커니즘을 사용 하는 경우 Visual Basic에서는 호출 코드에서 기본 프로그래밍 요소에 대 한 직접 참조를 프로시저에 제공 합니다.  
  
## <a name="passing-mechanism-and-element-type"></a>전달 메커니즘 및 요소 형식  
 전달 메커니즘의 선택은 요소 형식의 분류와 동일 합니다. 값 이나 참조로 전달 프로시저 코드에 제공 될 Visual Basic 참조 합니다. 값 형식 또는 참조 형식에는 프로그래밍 요소는 메모리에 저장 하는 방법을 참조 합니다.  
  
 그러나 전달 메커니즘 및 요소 형식이 서로 관련 되어 있습니다. 참조 형식의 값은 메모리의 다른 위치에서 데이터에 대 한 포인터입니다. 즉, 참조 형식 값으로 전달 하면 프로시저 코드에는 기본 요소 데이터에 대 한 포인터 요소 자체에 액세스할 수 없는 경우에 있습니다. 예를 들어 요소는 배열 변수, 프로시저 코드에는 변수 자체에 액세스할 수 없는 있지만 배열 멤버에 액세스할 수 있습니다.  
  
## <a name="ability-to-modify"></a>수정할 수 있는 기능  
 수정할 수 없는 요소를 인수로 전달 하면 프로시저 수정할 수 것 호출 코드에서 전달 되는 여부 `ByVal` 또는 `ByRef`합니다.  
  
 다음 표에서 수정할 수 있는 요소에 대 한 요소 형식 및 전달 메커니즘 간의 상호 작용 요약 되어 있습니다.  
  
|요소 형식|전달 `ByVal`|전달 `ByRef`|  
|------------------|--------------------|--------------------|  
|값 형식 (값만 포함)|프로시저 변수 또는 해당 멤버 중 하나를 변경할 수 없습니다.|프로시저가 변수 및 해당 멤버를 변경할 수 있습니다.|  
|참조 형식 (클래스 또는 구조체 인스턴스에 대 한 포인터 포함)|프로시저 변수 변경할 수 없지만 가리키는 인스턴스의 멤버를 변경할 수 있습니다.|프로시저 변수와 가리키는 인스턴스의 멤버 변경할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)  
 [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
