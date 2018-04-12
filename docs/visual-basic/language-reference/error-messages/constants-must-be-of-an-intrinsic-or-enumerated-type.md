---
title: 상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 702472751810c2d2bd08ece944ef0ffafc2049b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
형식 매개 변수를 포함 하는 제네릭 형식에 정의 된 또는 클래스, 구조체 또는 배열 형식으로 상수를 선언 하려고 했습니다.  
  
 상수는 내장 형식 이어야 합니다 (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, 또는 `UShort`), 또는 `Enum` 형식 정수 계열 형식 중 하나에 기반 합니다.  
  
 **오류 ID:** BC30424  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  내장 상수 선언 또는 `Enum` 유형입니다.  
  
2.  상수 수와 같은 특수 값이 될 수도 `True`, `False`, 또는 `Nothing`합니다. 컴파일러는 이러한 미리 정의 된 값이 적절 한 기본 유형일 수 있다고 간주 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [데이터 형식](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)
