---
title: 매개 변수와 인수의 차이점(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a5075c218371b754ac883b97475ab941811966b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650688"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>매개 변수와 인수의 차이점(Visual Basic)
대부분의 경우에서 프로시저 호출 된 있는 상황에 대 한 정보가 제공 되어야 합니다. 반복 또는 공유 작업을 수행 하는 프로시저는 각 호출에 대 한 다른 정보를 사용 합니다. 이 정보는 변수, 상수, 및 호출 하면 프로시저에 전달 하는 식으로 구성 됩니다.  
  
 이 정보를 프로시저에 전달 하기 위해 프로시저는 다음과 같이 정의 됩니다. 한 *매개 변수*, 호출 코드에서 전달 하 고는 *인수* 해당 매개 변수에 있습니다. 주차 공간으로 매개 변수 및 인수는 자동차 라고 생각할 수 있습니다. 방금 처럼 다른 자동차 수 주차 공간에서 서로 다른 시간에, 호출 코드 전달할 수 있습니다 다른 인수를 동일한 매개 변수에 한다는 프로시저를 호출할 때마다 합니다.  
  
## <a name="parameters"></a>매개 변수  
 A *매개 변수* 프로시저는 호출할 때 전달 되어야 하는 값을 나타냅니다. 프로시저의 선언 매개 변수를 정의합니다.  
  
 정의 하는 경우는 `Function` 또는 `Sub` 지정 프로시저는 *매개 변수 목록* 프로시저 이름 바로 다음 괄호로 합니다. 이름, 데이터 형식 및 전달 메커니즘 지정 각 매개 변수에 대해 ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). 매개 변수가 옵션 임을 나타낼 수 있습니다. 즉, 호출 코드에 대 한 값을 전달할 필요가 없습니다.  
  
 각 매개 변수의 이름은로 사용 된 *지역 변수* 절차에서 합니다. 다른 변수를 사용 하 여 동일한 방식으로 매개 변수 이름을 사용 합니다.  
  
## <a name="arguments"></a>인수  
 *인수* 는 프로시저를 호출할 때 프로시저 매개 변수에 전달 하는 값을 나타냅니다. 호출 하는 코드는 프로시저를 호출할 때 인수를 제공 합니다.  
  
 호출 하는 경우는 `Function` 또는 `Sub` 포함 하는 프로시저는 *인수 목록* 프로시저 이름 바로 다음 괄호로 합니다. 각 인수 목록에서 같은 위치에 매개 변수에 해당 합니다.  
  
 매개 변수 정의와 달리 인수의 이름이 필요 없습니다. 각 인수는 0 이상의 변수, 상수 및 리터럴 포함할 수 있는 식입니다. 계산된 식의 데이터 형식은 일반적으로 해당 매개 변수에 대해 정의 된 데이터 형식과 같아야 하 고 어떤 경우 든 매개 변수 형식으로 변환할 수 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [방법: 프로시저의 매개 변수 정의](./how-to-define-a-parameter-for-a-procedure.md)  
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [재귀 프로시저](./recursive-procedures.md)  
 [프로시저 오버로딩](./procedure-overloading.md)
