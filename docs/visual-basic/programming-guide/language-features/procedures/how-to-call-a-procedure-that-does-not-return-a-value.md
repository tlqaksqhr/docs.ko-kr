---
title: "방법: 값 (Visual Basic)를 반환 하지 않는 프로시저 호출 | Microsoft 문서"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
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
ms.openlocfilehash: 17b2b902f3ee6ab79b2614b7742aa08fefab2420
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>방법: 값을 반환하지 않는 프로시저 호출(Visual Basic)
A `Sub` 프로시저 호출 코드에 값을 반환 하지 않습니다. 이 명시적으로 호출 독립 실행형 호출 문을 사용 합니다. 식 내에서 프로시저 이름을 사용 하 여 호출할 수 없습니다.  
  
### <a name="to-call-a-sub-procedure"></a>Sub 프로시저를 호출 하려면  
  
1.  이름을 지정는 `Sub` 프로시저입니다.  
  
2.  괄호로 묶어 인수 목록 프로시저 이름 뒤에. 필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하는 코드를 읽기 쉽게.  
  
3.  인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다. 같은 순서로 인수를 지정 해야 하는 `Sub` 프로시저는 해당 매개 변수를 정의 합니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>응용 프로그램 창을 활성화 하는 함수입니다.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>창 제목 유일한 인수로 사용합니다.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 호출 코드에는 값을 반환 하지 않습니다. 예제에서는 throw <xref:System.ArgumentException>.</xref:System.ArgumentException> 메모장 프로세스를 실행 하지 않는 경우 `Shell` 절차에서는 응용 프로그램을 지정 된 경로 가정 합니다.  
  
     [!code-vb[VbVbalrCatRef #&11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException></xref:System.ArgumentException>   
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [방법: 프로시저 만들기](./how-to-create-a-procedure.md)   
 [방법: 값을 반환 하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)   
 [방법: Visual Basic에서 이벤트 처리기 호출](./how-to-call-an-event-handler.md)
