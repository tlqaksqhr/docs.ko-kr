---
title: "방법: 인수가 값 (Visual Basic)으로 전달 되도록 설정 | Microsoft 문서"
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
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
ms.openlocfilehash: eea3466534f1797170ae4bc72afbcba899929911
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>방법: 인수가 값으로 전달되도록 설정(Visual Basic)
프로시저 선언 전달 메커니즘을 결정 합니다. 매개 변수가 선언 된 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 참조로 해당 인수를 전달 하려면 필요 합니다. 이렇게 하면 호출 코드에서 인수를 기본 프로그래밍 요소의 값을 변경 하는 절차입니다. 이러한 변경 으로부터 내부 요소를 보호 하려는 경우 재정의할 수 있습니다는 `ByRef` 인수 이름을 괄호로 묶어 호출 프로시저에 전달 메커니즘입니다. 이 괄호는 호출에 인수 목록을 묶는 괄호는 별개입니다.  
  
 재정의할 수 없습니다. 호출 하는 코드는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘입니다.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>인수가 값으로 전달 되도록 설정 하려면  
  
-   해당 매개 변수가 선언 된 경우 `ByVal` 프로시저를 추가 단계를 수행할 필요가 있습니다. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]이미 값으로 인수 전달이 필요 합니다.  
  
-   해당 매개 변수가 선언 된 경우 `ByRef` 절차에서는 프로시저 호출에서 괄호 안에 인수를 묶습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 재정의 `ByRef` 매개 변수를 선언 합니다. 강제로 실행 하는 호출에서 `ByVal`, 괄호를 두 개를 기록해 둡니다.  
  
 [!code-vb[VbVbcnProcedures #&39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures #&40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 때 `str` 인수 목록에서 추가 괄호로 묶인는 `setNewString` 프로시저 호출 코드에서 해당 값을 변경할 수 없습니다 및 `MsgBox` "대체할 수 없는 byval로 전달 되는 경우"를 표시 합니다. 때 `str` 에 포함 되지 않은 추가 괄호 안의 프로시저를 변경할 수 및 `MsgBox` "inString 인수에 대 한 새 값입니다."를 표시 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 참조로 변수를 전달 하는 경우 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.  
  
 대화 상자에서 기본 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 값으로 인수를 전달 하는 것입니다. 그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 선언 된 모든 매개 변수를 사용 합니다. 이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 프로시저 매개 변수를 선언 하는 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)을 올바르게 실행 되는 코드의 호출 코드에서 기본 요소를 변경할 수 있는지에 따라 달라질 수 있습니다. 호출 코드에서 인수를 괄호로 묶어이 호출 하는 메커니즘을 재정의 하거나 수정할 수 없는 인수를 전달 하는 경우 프로시저는 내부 요소를 변경할 수 없습니다. 이 호출 코드에서 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 에 없는 경우 항상 한 잠재적인 위험을 호출 하는 코드에 있는 인수를 내부 값을 변경 하는 절차를 허용 합니다. 변경 되 고 사용 하기 전에 유효성을 검사할 수 있도록 준비 하려면이 값을 예상 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)   
 [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)   
 [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [참조 및 값으로 인수를 전달 간의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)   
 [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
