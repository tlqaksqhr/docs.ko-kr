---
title: 지역 형식 유추(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: b33b8b2d17c240e380377528d4f5d2f511381a7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655325"
---
# <a name="local-type-inference-visual-basic"></a>지역 형식 유추(Visual Basic)
Visual Basic 컴파일러를 사용 하 여 *형식 유추* 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 `As` 절. 컴파일러는 초기화 식의 형식에서 변수의 형식을 유추합니다. 그러면 다음 예제와 같이 형식을 명시적으로 선언 하지 않고 변수를 선언할 수 있습니다. 선언 결과로 둘 다 `num1` 및 `num2` 는 정수로 강력한 형식입니다.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  원하지 않는 경우 `num2` 형식으로 이전 예제에는 `Integer`, 같은 선언을 사용 하 여 다른 형식을 지정할 수 있습니다 `Dim num3 As Object = 3` 또는 `Dim num4 As Double = 3`합니다.  

> [!NOTE]
>  형식 유추에서 비정적 지역 변수;에 사용할 수 있습니다. 클래스 필드, 속성 또는 함수 형식을 사용할 수 없습니다.
 
 지역 형식 유추는 프로시저 수준에서 적용 됩니다. (클래스, 구조체, 모듈 또는 인터페이스를 제외한 내 블록 또는 프로시저일) 모듈 수준 변수를 선언 하는 사용할 수 없습니다. 경우 `num2` 이전 예제에서 프로시저의 지역 변수 대신 클래스의 필드에서 선언 된 오류를 발생 시키는 `Option Strict` on, 분류 및 `num2` 로 `Object` 와 `Option Strict` 해제 합니다. 마찬가지로, 지역 형식 유추로 선언 된 프로시저 수준 변수에 적용 되지 않습니다 `Static`합니다.  
  
## <a name="type-inference-vs-late-binding"></a>형식 유추와 런타임에 바인딩  
 형식 유추를 사용 하는 코드는 런타임에 바인딩을 사용 하는 코드와 유사 합니다. 그러나 형식 유추로 두는 대신 변수를 강력한 형식 `Object`합니다. 컴파일러는 변수 이니셜라이저를 사용 하 여 초기 바인딩 코드를 생성 하기 위해 컴파일 타임에 다음이 변수의 유형을 확인할 수 있습니다. 이전 예에서 `num2`처럼 `num1`로 형식화 되는 `Integer`합니다.  
  
 런타임에 바인딩된 변수를 런타임에만 형식이 알려져의 초기 바인딩된 변수의 동작은 다릅니다. 초기 형식을 알 컴파일러를를 실행 하기 전에 문제를 식별, 정확 하 게, 메모리 할당 및 기타 최적화를 수행할 수 있습니다. 초기 바인딩 Visual Basic 통합된 개발 환경을 (IDE) 개체의 멤버에 대 한 IntelliSense 도움말을 사용할 수 있도록 해줍니다. 초기 바인딩 성능에 대 한 기본 설정 이기도합니다. 런타임에 바인딩된 변수에 저장 된 모든 데이터 형식으로 래핑되어야 때문에 이것이 `Object`, 속도가 느린 프로그램을 사용 하면 런타임에 형식의 멤버에 액세스 합니다.  
  
## <a name="examples"></a>예제  
 형식 유추는 지역 변수를 선언 하지 하는 경우에 발생 한 `As` 절 되 고 초기화 합니다. 변수의 유형으로 할당 된 초기 값의 형식을 사용 하는 컴파일러입니다. 코드의 다음 줄은 각각 형식의 변수 선언 하는 예를 들어 `String`합니다.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 다음 코드에는 정수의 배열을 만드는 데 두 해당 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 형식 유추를 사용 하 여 루프 제어 변수의 형식을 결정 하는 것이 유용 합니다. 다음 코드에서는 컴파일러에서 유추 하는 `number` 는 `Integer` 때문에 `someNumbers2` 이전 예제에서 정수 배열이 됩니다.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 지역 형식 유추에서 사용할 수 있습니다 `Using` 다음 예제에서 보여 주듯이 리소스 이름의 형식을 설정 하는 문입니다.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 다음 예제에서 보여 주듯이 변수 형식은 함수, 반환 값에서 유추할 수도 합니다. 둘 다 `pList1` 및 `pList2` 때문에 프로세스의 배열 `Process.GetProcesses` 프로세스의 배열을 반환 합니다.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer` 지역 형식 유추 특정 파일에서 허용 되는지 여부를 지정할 수 있습니다. 사용 하도록 설정 하려면 또는 옵션을 차단 하는 파일의 시작 부분에 다음 문 중 하나를 입력 합니다.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 에 대 한 값을 지정 하지 않으면 `Option Infer` 컴파일러 기본값은 코드에서 `Option Infer On`합니다. 업그레이드 된 프로젝트에 대해 [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] 컴파일러 기본값은 이전 버전에서는 `Option Infer Off`합니다.  
  
 파일에서 `Option Infer`에 대해 설정된 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우에는 파일의 값이 우선적으로 적용됩니다.  
  
 자세한 내용은 참조 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 문](../../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
