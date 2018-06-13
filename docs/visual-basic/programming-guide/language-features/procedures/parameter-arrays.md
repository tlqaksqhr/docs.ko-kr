---
title: 매개 변수 배열(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: a91da0d9e16ff11fdd4980588fee64b3e4a603c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652379"
---
# <a name="parameter-arrays-visual-basic"></a>매개 변수 배열(Visual Basic)
일반적으로 프로시저 선언에 지정 하는 보다 많은 인수를 사용 하 여 프로시저를 호출할 수 없습니다. 불특정 개수의 인수를 필요한 경우를 선언할 수 있습니다는 *매개 변수 배열*, 프로시저 매개 변수에 대해 값의 배열을 수락 하도록 허용 하는 합니다. 프로시저를 정의할 때 매개 변수 배열에 있는 요소의 수를 알 필요가 없습니다. 배열 크기는 각 프로시저를 호출 하 여 개별적으로 결정 됩니다.  
  
## <a name="declaring-a-paramarray"></a>ParamArray 선언  
 사용 된 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 키워드를 나타내는 매개 변수 목록에서 매개 변수 배열입니다. 이 때 적용되는 규칙은 다음과 같습니다.  
  
-   프로시저 매개 변수 배열을 하나만 정의 하 고 프로시저 정의의 마지막 매개 변수 여야 합니다.  
  
-   매개 변수 배열의 값으로 전달 되어야 합니다. 것이 바람직한 프로그래밍 습관 명시적으로 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 프로시저 정의에 키워드입니다.  
  
-   매개 변수 배열은 자동으로 선택 사항입니다. 기본값은 빈 1 차원 배열 매개 변수 배열 요소 형식입니다.  
  
-   앞에 매개 변수 배열의 모든 매개 변수는 필수 여야 합니다. 매개 변수 배열에는 선택적 매개 변수 여야 합니다.  
  
## <a name="calling-a-paramarray"></a>ParamArray를 호출합니다.  
 매개 변수 배열을 정의 하는 프로시저를 호출할 때 다음 방법 중 하나에서는 인수를 제공할 수 있습니다.  
  
-   아무것도-즉, 생략할 수 있습니다는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 인수입니다. 이 경우 빈 배열은 프로시저에 전달 됩니다. 전달할 수도 있습니다는 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 결과 동일 합니다.  
  
-   임의의 수의 인수를 쉼표로 구분 된 목록입니다. 각 인수의 데이터 형식을 암시적으로 변환할 수 있어야는 `ParamArray` 요소 형식입니다.  
  
-   동일한 요소와 배열 매개 변수 배열 요소 형식으로 입력 합니다.  
  
 모든 경우에는 프로시저의 코드 취급 하는 매개 변수 배열을으로 동일한 데이터 형식의 요소만 있는 1 차원 배열에서 `ParamArray` 데이터 형식입니다.  
  
> [!IMPORTANT]
>  무한정 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다. 매개 변수 배열에 동의 하면 호출 코드에서 전달 된 배열의 크기에 대 한 테스트 해야 합니다. 응용 프로그램에 대해 너무 큰 경우 적절 한 단계를 수행 합니다. 자세한 내용은 참조 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 하 고 함수를 호출 `calcSum`합니다. `ParamArray` 매개 변수 한정자 `args` 가변 개수의 인수를 수락 하는 함수를 사용 하도록 설정 합니다.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 다음 예제에서는 매개 변수 배열에 있는 프로시저를 정의 하 고 해당 매개 변수 배열에 전달 되는 모든 배열 요소 값을 출력 합니다.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)  
 [선택적 매개 변수](./optional-parameters.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [선택 사항](../../../../visual-basic/language-reference/modifiers/optional.md)
