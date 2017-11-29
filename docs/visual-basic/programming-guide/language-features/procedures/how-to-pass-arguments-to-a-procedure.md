---
title: "방법: 프로시저에 인수 전달(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3debb4fa6e7b15f9c321ef207d0cc04181a98da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>방법: 프로시저에 인수 전달(Visual Basic)
프로시저를 호출 하는 경우에 인수 목록 괄호로 묶어 프로시저 이름 뒤에. 프로시저에 정의 된 모든 필수 매개 변수에 해당 하는 인수를 제공 하 고 인수를 선택적으로 제공할 수는 `Optional` 매개 변수입니다. 지정 하지 않으면 프로그램 `Optional` 호출에 매개 변수를 모든 후속 인수를 제공 하는 경우 인수 목록에 해당 위치를 표시 하려면 쉼표를 포함 해야 합니다.  
  
 데이터 형식의 인수를 등의 해당 매개 변수를 전달 하려는 경우 `Byte` 를 `String`, 형식 검사 스위치를 설정할 수 있습니다 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))를 `Off`합니다. 경우 `Option Strict` 은 `On`, 하나를 사용 해야 확대 변환 또는 명시적 변환 키워드입니다. 자세한 내용은 참조 [확장 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.  
  
 자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>프로시저에 하나 이상의 인수를 전달 하려면  
  
1.  호출 문에서 프로시저 이름을 뒤에 괄호를 따릅니다.  
  
2.  괄호 안에 인수 목록을 추가 합니다. 프로시저에 정의 필요한 각 매개 변수에 대 한 인수를 포함 하 고 인수는 쉼표로 구분 합니다.  
  
3.  각 인수는 해당 매개 변수에 대 한 프로시저 형식으로 변환할 수 있는 데이터 형식으로 계산 되는 유효한 식 정의 있는지 확인 합니다.  
  
4.  매개 변수가 정의 되어 있으면 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), 인수 목록에 포함 하거나 생략할 수 있습니다. 를 생략 하면 프로시저는 해당 매개 변수에 대해 정의 된 기본값으로 값을 사용 합니다.  
  
5.  에 대 한 인수를 생략 하는 경우는 `Optional` 매개 변수 및 매개 변수 목록 뒤에 다른 매개 변수가 있는, 인수 목록에 여분의 쉼표 여 생략 된 인수의 위치를 표시할 수 있습니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수입니다.  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     앞의 예제에는 표시할 메시지 문자열 필요한 첫 번째 인수를 제공 합니다. 메시지 상자에 표시할 단추를 지정 하는 선택적 두 번째 매개 변수에 인수를 생략 합니다. 통화 값을 제공 하지 않는 때문에 `MsgBox` 기본값을 사용 `MsgBoxStyle.OKOnly`만 표시 하는 **확인** 단추입니다.  
  
     인수 목록에 두 번째 쉼표는 생략 두 번째 인수의 위치를 표시 하 고 마지막 문자열의 선택적 세 번째 매개 변수에 전달 되 `MsgBox`, 제목 표시줄에 표시할 텍스트 이며 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [방법: 프로시저의 매개 변수 정의](./how-to-define-a-parameter-for-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [재귀 프로시저](./recursive-procedures.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
