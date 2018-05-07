---
title: '방법: 선택적 매개 변수를 사용하는 프로시저 오버로드(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 1da1d67726a9669477721aabc0aace0119aa7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a>방법: 선택적 매개 변수를 사용하는 프로시저 오버로드(Visual Basic)
프로시저에 있는 경우 하나 이상의 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수를 암시적 오버 로드 중 하나를 일치 하는 오버 로드 된 버전을 정의할 수 없습니다. 자세한 내용은 "암시적 오버 로드에 대 한 선택적 매개 변수"를 참조 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
## <a name="one-optional-parameter"></a>하나의 선택적 매개 변수  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a>하나의 선택적 매개 변수를 사용 하는 프로시저 오버 로드 하려면  
  
1.  쓰기는 `Sub` 또는 `Function` 매개 변수 목록에서 선택적 매개 변수를 포함 하는 선언문입니다. 사용 하지 않는 `Optional` 이 오버 로드 된 버전의 키워드입니다.  
  
2.  앞에 `Sub` 또는 `Function` 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.  
  
3.  호출 코드 선택적 인수를 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.  
  
4.  사용 하 여 프로시저를 종료는 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.  
  
5.  동일 하 게 첫 번째 선언에는 선택적 매개 변수는 매개 변수 목록에 포함 되지 않습니다는 점을 제외 하 고 두 번째 선언 문을 작성 합니다.  
  
6.  호출 코드에서 선택적 인수를 제공 하지 않는 경우 실행 해야 하는 프로시저 코드를 작성 합니다. 사용 하 여 프로시저를 종료는 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.  
  
     다음 예에서는 선택적 매개 변수, 해당 집합의 두 개의 오버 로드 된 프로시저를 마지막으로 목록과 잘못 된 하 고 올바른 오버 로드 된 버전을 사용 하 여 정의 하는 프로시저를 보여 줍니다.  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a>여러 선택적 매개 변수  
 일반적으로 둘 이상의 선택적 매개 변수를 사용 하 여 프로시저를 두 개 이상의 오버 로드 된 버전 필요. 예를 들어 되는 두 가지 선택적 매개 변수를 호출 하는 코드 수 제공 하거나 서로 독립적으로 하나씩을 생략할 경우 제공 된 인수의 가능한 각 조합에 대해 하나씩 네 개의 오버 로드 된 버전이 필요 합니다.  
  
 선택적 매개 변수 수가 늘어나면 오버 로드의 복잡성이 증가 합니다. 제공 된 인수의 일부 조합은 허용 되지 않는 경우가 아니면 N 선택적 매개 변수에 대해 필요한 2 ^ N 오버 로드 된 버전입니다. 프로시저의 특성에 따라는 논리의 선명도 들여야 모든 오버 로드 된 버전을 정의 발견할 수 있습니다.  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a>둘 이상의 선택적 매개 변수를 사용 하는 프로시저 오버 로드 하려면  
  
1.  프로시저의 논리에 따라 허용 제공 된 선택적 인수의 조합을 결정 합니다. 다른 종속 되는 하나의 선택적 매개 변수는 허용 되지 않는 조합 발생할 수 있습니다. 예를 들어 매개 변수가 하나 배우자의 이름을 허용 하 고 배우자의 나이 적용 하는 다른, 하는 경우 보존 기간을 제공 하지만 이름을 생략 인수의 조합 허용 되지 않습니다 됩니다.  
  
2.  제공 된 선택적 인수의 각 허용 가능한 조합에 대해 작성 한 `Sub` 또는 `Function` 해당 매개 변수 목록을 정의 하는 선언문입니다. 사용 하지 않는 `Optional` 키워드입니다.  
  
3.  각 선언 앞에 `Sub` 또는 `Function` 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.  
  
4.  각각의 선언이 호출 코드에 해당 선언이 매개 변수 목록에 해당 하는 인수 목록을 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.  
  
5.  각 프로시저를 종료는 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [선택적 매개 변수](./optional-parameters.md)  
 [매개 변수 배열](./parameter-arrays.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [프로시저 문제 해결](./troubleshooting-procedures.md)  
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)  
 [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)  
 [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [오버로드 확인](./overload-resolution.md)
