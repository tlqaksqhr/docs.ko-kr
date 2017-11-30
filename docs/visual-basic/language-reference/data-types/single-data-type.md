---
title: "Single 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a>Single 데이터 형식(Visual Basic)
부호 있는 IEEE 32 비트 (4 바이트) 단 정밀도 부동 소수점 숫자 값의 범위가-3.4028235 e + 38에서 저장-1.401298 e을 통해-음수 값 1.401298 e에서 45-45 3.4028235 e + 38 양수 값에 대 한 합니다. 단 정밀도 수는 실수의 근사값을 저장 합니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `Single` 데이터 형식으로의 데이터를 전체 너비가 필요 하지 않은 부동 소수점 값을 저장할 `Double`합니다. 일부 경우에 공용 언어 런타임 압축할 수 있습니다 프로그램 `Single` 변수 긴밀 한 협력을 및 메모리 소비를 저장 합니다.  
  
 `Single`의 기본값은 0입니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **전체 자릿수입니다.** 부동 소수점 숫자를 작업할 때는 항상 없는 정확한 표시 메모리에 염두에 둬야 합니다. 값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 `Mod` 연산자입니다. 자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
-   **확대 합니다.** `Single` 데이터 형식으로 확대 되 `Double`합니다. 즉, 변환할 수 `Single` 를 `Double` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.  
  
-   **뒤에 오는 0입니다.** 부동 소수점 데이터 형식 후행 0 문자의 모든 내부 표현이 없습니다. 예를 들어 이러한 구분 하지 않습니다 4.2000 및 4.2 합니다. 따라서 후행 0 문자 표시 하거나 부동 소수점 값을 인쇄 하는 경우에 표시 되지 않습니다.  
  
-   **형식 문자입니다.** 리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다. 식별자 형식 문자 `!`를 식별자에 추가하면 `Single`가 됩니다.  
  
-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Single?displayProperty=nameWithType>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Decimal 데이터 형식](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
