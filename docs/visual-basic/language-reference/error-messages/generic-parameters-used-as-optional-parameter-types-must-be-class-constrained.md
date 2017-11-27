---
title: "선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords: BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다.
프로시저는 참조 형식으로 제한 되지 않은 형식 매개 변수를 사용 하는 선택적 매개 변수로 선언 됩니다.  
  
 항상 각 선택적 매개 변수에 기본값을 제공 해야 합니다. 선택적 값 이어야 합니다는 매개 변수는 참조 형식의 경우 `Nothing`, 참조 형식에 대 한 유효한 값은입니다. 그러나 매개 변수는 값 형식의 경우 해당 형식이 Visual Basic에서 미리 정의 된 기본 데이터 형식 이어야 합니다. 사용자 정의 구조와 같은 복합 값 형식에 유효한 기본값이 없는 때문입니다.  
  
 형식 매개 변수는 선택적 매개 변수를 사용 하 여 유효한 기본값이 없고 값 형식의 문제를 방지 하려면 참조 형식의 임을 확인 해야 합니다. 즉, 형식 매개 변수를 사용 하 여 제한 해야는 `Class` 키워드 또는 특정 클래스의 이름입니다.  
  
 **오류 ID:** BC32124  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   형식 매개 변수는 참조 형식을 제한 하거나 선택적 매개 변수를 사용 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
