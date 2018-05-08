---
title: '방법: 여러 버전의 프로시저 정의(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: a4d0c5bbb07dd5433ff62179fc10a6274bf19364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>방법: 여러 버전의 프로시저 정의(Visual Basic)
여러 버전으로 프로시저를 정의할 수 *오버 로드* 이름은 동일 하지만 다른 매개 변수 목록을 사용 하 여 각 버전에 대 한 것입니다. 오버 로드의 목적은 이름을 다르게 필요 없이 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다.  
  
 자세한 내용은 참조 [프로시저 오버 로드](./procedure-overloading.md)합니다.  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>여러 버전의 프로시저를 정의 하려면  
  
1.  쓰기는 `Sub` 또는 `Function` 선언문 정의 하려면 프로시저의 각 버전에 대 한 합니다. 모든 선언에 이름이 같은 프로시저를 사용 합니다.  
  
2.  앞의 `Sub` 또는 `Function` 각 선언에서 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다. 선택적으로 생략할 수 `Overloads` 선언 중 하나에 포함 하는 경우를 제외한 선언에 포함 해야 모든 선언에 있습니다.  
  
3.  각 선언문 뒤 호출 코드에서 해당 버전의 매개 변수 목록과 일치 하는 인수를 제공 하는 여기서 특정 경우를 처리 하는 프로시저 코드를 작성 합니다. 않아도 테스트 하려면 호출 코드에서 제공한 매개 변수입니다. Visual Basic에서는 프로시저의 짝이 되는 버전 제어를 전달합니다.  
  
4.  사용 하 여 프로시저의 각 버전을 종료는 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `Sub` 고객의 균형에 대 한 트랜잭션을 게시 하는 프로시저입니다. 사용 하 여는 `Overloads` 하나 이름 및 다른 고객 계정 번호를 허용 하는 프로시저의 두 버전을 정의 하는 키워드입니다.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 호출 코드로 고객 id를 가져올 수는 `String` 또는 `Integer`, 다음 두 경우 모두 동일한 호출 문을 사용 하 여 합니다.  
  
 이러한 버전을 호출 하는 방법에 대 한 내용은 `post` 프로시저 참조 [하는 방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 프로시저 이름은 동일 하지만 다른 매개 변수 목록 각 오버 로드 된 버전에 있는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [프로시저 문제 해결](./troubleshooting-procedures.md)  
 [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)  
 [오버로드 확인](./overload-resolution.md)
