---
title: 상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 4d635d289ed99aed48c296c278bc546971af51da
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999203"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
클래스, 구조체 또는 배열 형식 또는 형식 매개 변수를 포함 하는 제네릭 형식에 의해 정의 된 상수를 선언 하려고 했습니다.  
  
 상수 내장 형식 이어야 합니다 (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`를 `Integer`, `Long`를 `Object`, `SByte`를 `Short`, `Single`, `String`, `UInteger`를 `ULong`, 또는 `UShort`), 또는 `Enum` 형식이 정수 형식 중 하나에 따라 합니다.  
  
 **오류 ID:** BC30424  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  내장 함수로 상수를 선언 하거나 `Enum` 형식입니다.  
  
2.  상수 수와 같은 특수 값이 될 수도 `True`하십시오 `False`, 또는 `Nothing`합니다. 컴파일러는 적절 한 내장 형식으로 이러한 미리 정의 된 값을 고려 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [데이터 형식](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)
