---
title: "방법: 프로시저 (Visual Basic)에서 값 반환 | Microsoft 문서"
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
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 98f0fb0740a021a16e87454bfaebbfad7858477c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>방법: 프로시저에서 값 반환(Visual Basic)
A `Function` 프로시저에 값을 반환 호출 코드를 실행 하 여 하나는 `Return` 문 또는 발생 하 여는 `Exit Function` 또는 `End Function` 문입니다.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Return 문을 사용 하 여 값을 반환 하려면  
  
1.  배치는 `Return` 프로시저의 작업이 완료 되는 지점에 문의 합니다.  
  
2.  에 따라는 `Return` 호출 코드로 반환 하려는 키워드 값을 생성 하는 식입니다.  
  
3.  둘 이상의 `Return` 동일한 절차에는 문입니다.  
  
     다음 `Function` 프로시저 가장 긴 면 또는 직각 삼각형의 빗변을 계산 하 고 호출 코드에 반환 합니다.  
  
     [!code-vb[VbVbcnProcedures #&1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     다음 예제에서는 호출을 `hypotenuse`, 반환된 된 값을 저장 하는 합니다.  
  
     [!code-vb[VbVbcnProcedures #&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Exit 함수 또는 End 함수를 사용 하 여 값을 반환 하려면  
  
1.  하나 이상의 위치에는 `Function` 프로시저는 프로시저의 이름으로이 값을 할당 합니다.  
  
2.  실행 하는 경우는 `Exit Function` 또는 `End Function` 문을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로시저의 이름에 가장 최근에 할당 된 값을 반환 합니다.  
  
3.  둘 이상의 `Exit Function` 문을 동일한 절차에 혼합할 수 `Return` 및 `Exit Function` 동일한 프로시저의 문이 있습니다.  
  
4.  하나씩만 있을 수 `End Function` 문에서 `Function` 프로시저입니다.  
  
     자세한 내용 및 예제에 대 한 "반환 값이"의 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [속성 프로시저](./property-procedures.md)   
 [연산자 프로시저](./operator-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return 문](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [방법: 값을 반환 하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)   
 [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
