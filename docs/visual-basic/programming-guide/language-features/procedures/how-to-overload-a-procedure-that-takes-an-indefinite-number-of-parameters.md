---
title: "방법: 불특정 개수의 매개 변수 (Visual Basic)를 사용 하는 프로시저 오버 로드 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c7e09bd482e35c7ce7f28a6cc7de0379b7cc89f6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드(Visual Basic)
프로시저에 있는 경우는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수를&1; 차원 배열을 매개 변수 배열에 대 한 오버 로드 된 버전을 정의할 수 없습니다. 자세한 내용은 "암시적 오버 로드에 대 한 a ParamArray 매개 변수 참조"에서 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>가변 개수의 매개 변수를 사용 하는 프로시저 오버 로드 하려면  
  
1.  코드 논리 혜택이 호출 하는 프로시저 오버 로드 된 버전 이상에서 확인 한 `ParamArray` 매개 변수입니다. "오버 로드 및 ParamArrays" 참조 [프로시저를 오버 로드할 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
2.  제공 된 값의 숫자는 매개 변수 목록의 변수 부분에서 프로시저를 허용 해야 결정 합니다. 이 값이 없는 경우 포함 하며 단일&1; 차원 배열의 경우 포함 될 수 있습니다.  
  
3.  제공 된 값의 허용 가능한 각 번호에 대 한 쓰기는 `Sub` 또는 `Function` 해당 매개 변수 목록을 정의 하는 선언문입니다. 사용 하지 않는 `Optional` 또는 `ParamArray` 이 오버 로드 된 버전의 키워드입니다.  
  
4.  각 선언 앞에 `Sub` 또는 `Function` 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.  
  
5.  각각의 선언이 호출 코드에서 해당 선언 매개 변수 목록에 해당 하는 값을 제공 하는 경우 실행 해야 하는 프로시저 코드를 작성 합니다.  
  
6.  각 프로시저를 종료는 `End Sub` 또는 `End Function` 문을 적절 하 게 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 정의 하는 프로시저는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 및 오버 로드 된 프로시저의 해당 집합입니다.  
  
 [!code-vb[VbVbcnProcedures #&69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures #&70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 매개 변수 배열에 대 한&1; 차원 배열을 사용 하는 매개 변수 목록으로는 이러한 프로시저를 오버 로드할 수 없습니다. 그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다. 다음과 같은 선언을 이러한 경우를 설명 합니다.  
  
 [!code-vb[VbVbcnProcedures #&71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 오버 로드 된 버전의에서 코드는 호출 코드에 대 한 하나 이상의 값을 제공 했는지 여부를 테스트 하지 않아도 `ParamArray` 매개 변수를 했다면 수 있습니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]호출 인수 목록과 일치 하는 버전으로 제어가 전달 됩니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 때문에 프로시저는 `ParamArray` 매개 변수는 오버 로드 된 버전의 집합, 이러한 암시적 오버 로드 중 하나에 해당 하는 매개 변수 목록으로는 이러한 프로시저를 오버 로드할 수 없습니다. 자세한 내용은 참조 [프로시저 오버 로드의 고려 사항](./considerations-in-overloading-procedures.md)합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 무한정 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 몇 가지 내부 용량에 오버런이 위험이 있습니다. 매개 변수 배열에 동의 하면 호출 코드에 전달 된 배열의 길이 대 한 테스트 하 고 응용 프로그램에 대해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [선택적 매개 변수](./optional-parameters.md)   
 [매개 변수 배열](./parameter-arrays.md)   
 [프로시저 오버 로드](./procedure-overloading.md)   
 [문제 해결 절차](./troubleshooting-procedures.md)   
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)   
 [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)   
 [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [오버로드 확인](./overload-resolution.md)
