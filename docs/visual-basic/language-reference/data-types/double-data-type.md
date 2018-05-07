---
title: Double 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: c2d3d7d360ccb240bafbe0e19e9f396adfba7f7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="double-data-type-visual-basic"></a>Double 데이터 형식(Visual Basic)
부호 있는 IEEE 64 비트 (8 바이트) 배정밀 부동 소수점 숫자 값에서-1.79769313486231570 e + 308에서-범위에 있는 저장 4.94065645841246544E-324 음수 경우 4.94065645841246544 e에서-324 1.79769313486231570 e + 308 양수 값입니다. 두 자리 숫자는 실수의 근사값을 저장합니다.  
  
## <a name="remarks"></a>설명  
 `Double` 숫자 데이터 형식을 사용할 수 있는 가장 큰와 가장 작은 크기를 제공 합니다.  
  
 `Double`의 기본값은 0입니다.  
  
## <a name="programming-tips"></a>프로그래밍 팁  
  
-   **전체 자릿수입니다.** 부동 소수점 숫자를 작업할 때에 항상 없는 정확한 표시 메모리에 해야 합니다. 값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 `Mod` 연산자입니다. 자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
-   **뒤에 오는 0입니다.** 부동 소수점 데이터 형식에는 후행 0 문자 모든 내부 표현이지 않습니다. 예를 들어 이러한 구분 하지 않습니다 4.2000 및 4.2 합니다. 따라서 후행 0 문자를 표시할 때 또는 인쇄 부동 소수점 값 표시 되지 않습니다.  
  
-   **형식 문자입니다.** 리터럴 형식 문자 `R`를 리터럴에 추가하면 `Double` 데이터 형식이 됩니다. 예를 들어, 다음에 정수 값 되 면 `R`, 값이 변경 되는 `Double`합니다.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     식별자 형식 문자 `#`를 식별자에 추가하면 `Double`가 됩니다. 다음 예에서 변수 `num` 로 형식화 되는 `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Framework 형식입니다.** .NET Framework에서 해당하는 형식은 <xref:System.Double?displayProperty=nameWithType> 구조체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Double?displayProperty=nameWithType>  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Decimal 데이터 형식](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Single 데이터 형식](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [데이터 형식의 효율적 사용](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
