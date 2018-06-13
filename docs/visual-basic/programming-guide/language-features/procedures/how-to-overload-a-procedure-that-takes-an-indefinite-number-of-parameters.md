---
title: '방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 026dd59db135e8b195ae014aaff5e3a6a7846fc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651494"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드(Visual Basic)
프로시저에 있는 경우는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수를 1 차원 배열을 매개 변수 배열에 대 한 오버 로드 된 버전을 정의할 수 없습니다. 자세한 내용은 "암시적 오버 로드에 대 한는 ParamArray 매개 변수"를 참조 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>가변 개수의 매개 변수를 사용 하는 프로시저 오버 로드 하려면  
  
1.  코드 논리 혜택을 호출 하 고 해당 프로시저가 버전 이상에서 오버 로드 되었음을 확인 한 `ParamArray` 매개 변수입니다. "오버 로드 및 ParamArrays" 참조 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
2.  제공 된 값의 숫자는 프로시저는 매개 변수 목록에에서 적용 해야 할 것을 확인 합니다. 값이 없는 경우 포함 하 고 단일 1 차원 배열의 대/소문자를 포함 될 수 있습니다.  
  
3.  제공 된 값의 각 허용 되는 번호를 작성 한 `Sub` 또는 `Function` 해당 매개 변수 목록을 정의 하는 선언문입니다. 사용 하지 않는 `Optional` 또는 `ParamArray` 이 오버 로드 된 버전의 키워드입니다.  
  
4.  각 선언 앞에 `Sub` 또는 `Function` 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.  
  
5.  각각의 선언이 호출 코드 해당 선언의 매개 변수 목록에 해당 하는 값을 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.  
  
6.  각 프로시저를 종료는 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 프로시저를 사용 하 여 정의 보여 줍니다.는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 및 오버 로드 된 프로시저의 해당 집합입니다.  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 매개 변수 배열에 대 한 1 차원 배열을 사용 하는 매개 변수 목록으로 이러한 프로시저를 오버 로드할 수 없습니다. 그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다. 다음 선언을 이러한 경우를 설명 합니다.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 오버 로드 된 버전의에서 코드 호출 코드에 대 한 하나 이상의 값을 제공 했는지 여부를 테스트 하지 않아도 `ParamArray` 매개 변수를 그렇다면 또는 개수입니다. Visual Basic에서는 호출 인수 목록과 일치 하는 버전 제어를 전달 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 때문에 있는 프로시저는 `ParamArray` 매개 변수는 오버 로드 된 버전 집합, 이러한 암시적 오버 로드 중 하나에 해당 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 자세한 내용은 참조 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 무한정 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다. 매개 변수 배열에 동의 하면 호출 코드에 전달 된 배열의 길이 대 한 테스트 하 고 응용 프로그램에 대해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [선택적 매개 변수](./optional-parameters.md)  
 [매개 변수 배열](./parameter-arrays.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [프로시저 문제 해결](./troubleshooting-procedures.md)  
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)  
 [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)  
 [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [오버로드 확인](./overload-resolution.md)
