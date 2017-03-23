---
title: "방법: 여러 버전의 프로시저 (Visual Basic)를 정의 합니다. | Microsoft 문서"
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
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
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
ms.openlocfilehash: 0228083ce00a0f552227fd7ae8f0f5a24f65148e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>방법: 여러 버전의 프로시저 정의(Visual Basic)
여러 버전으로 프로시저를 정의할 수 *오버 로드* 이름은 동일 하지만 다른 매개 변수 목록을 사용 하 여 각 버전에 대 한 것입니다. 오버 로드의 목적은 이름을 다르게 하지 않고 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다.  
  
 자세한 내용은 참조 [프로시저 오버 로딩](./procedure-overloading.md)합니다.  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>여러 버전의 프로시저를 정의 하려면  
  
1.  쓰기는 `Sub` 또는 `Function` 정의 하려는 프로시저의 각 버전에 대 한 선언문입니다. 모든 선언에서 동일한 프로시저 이름을 사용 합니다.  
  
2.  앞에 `Sub` 또는 `Function` 각 선언에서 키워드는 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다. 생략 해도 `Overloads` 선언 중 하나에 포함 하는 경우를 제외한 선언에 포함 해야 모든 선언에 있습니다.  
  
3.  각 선언문 뒤 호출 코드에서 해당 버전의 매개 변수 목록과 일치 하는 인수를 제공 하는 여기서 특정 경우를 처리 하도록 프로시저 코드를 작성 합니다. 필요가 없습니다 테스트 하는 매개 변수에 대 한 호출 코드에 제공 합니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 프로시저의 일치 하는 버전으로 제어가 전달 됩니다.  
  
4.  각 버전을 사용 하 여 프로시저의 종료는 `End Sub` 또는 `End Function` 문을 적절 하 게 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `Sub` 고객의 잔고에 대 한 트랜잭션을 게시 하는 프로시저입니다. 사용 하 여는 `Overloads` 이름 및 다른 고객 계정 번호를 허용 하는 프로시저의 두 버전을 정의 하는 키워드입니다.  
  
 [!code-vb[VbVbcnProcedures #&72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 호출 코드로 고객 id를 가져올 수는 `String` 또는 `Integer`, 다음 두 경우 모두 동일한 호출 문을 사용 하 여 합니다.  
  
 이러한 버전을 호출 하는 방법에 대 한 내용은 `post` 프로시저 참조 [하는 방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 각 오버 로드 된 버전이 프로시저 이름은 동일 하지만 다른 매개 변수 목록에 있는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [문제 해결 절차](./troubleshooting-procedures.md)   
 [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)   
 [오버로드 확인](./overload-resolution.md)
