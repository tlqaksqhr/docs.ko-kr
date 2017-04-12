---
title: "방법: 프로시저 (Visual Basic)에 인수를 전달 합니다. | Microsoft 문서"
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
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
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
ms.openlocfilehash: ddccd476b2347368d0435f637edf3882db306f45
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>방법: 프로시저에 인수 전달(Visual Basic)
프로시저를 호출 하는 경우에 인수 목록 괄호로 묶어 프로시저 이름 뒤에. 프로시저를 정의 하는 모든 필수 매개 변수에 해당 하는 인수를 제공 하 고에 대 한 인수를 선택적으로 제공할 수는 `Optional` 매개 변수입니다. 지정 하지 않으면는 `Optional` 호출에서 매개 변수를 모든 후속 인수를 제공 하는 경우 인수 목록에서 해당 위치를 표시 하는 쉼표를 포함 해야 합니다.  
  
 데이터 형식의 인수를와 같은 서로 다른 지는 해당 매개 변수로 전달 하려는 경우 `Byte` 를 `String`, 형식 검사 스위치를 설정할 수 있습니다 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))를 `Off`합니다. 경우 `Option Strict` 는 `On`, 하나를 사용 해야 확대 변환 또는 명시적 변환 키워드입니다. 자세한 내용은 참조 [확장 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.  
  
 자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>프로시저에 하나 이상의 인수를 전달 하려면  
  
1.  문 호출 프로시저 이름을 뒤에 괄호를 따릅니다.  
  
2.  괄호 안에 인수 목록을 넣습니다. 프로시저에 정의 필요한 각 매개 변수에 대 한 인수를 포함 하 고 인수를 쉼표로 구분 합니다.  
  
3.  각 인수는 해당 매개 변수에 대 한 프로시저 형식으로 변환할 수 있는 데이터 형식으로 계산 되는 유효한 식 정의 해야 합니다.  
  
4.  매개 변수가 정의 되어 있으면 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md)를 인수 목록에 포함 하거나 생략할 수 있습니다. 를 생략 하면 프로시저는 해당 매개 변수에 대해 정의 된 기본값을 사용 합니다.  
  
5.  에 대 한 인수를 생략 하면는 `Optional` 매개 변수 및 매개 변수 목록 뒤에 다른 매개 변수가 있는, 인수 목록에 여분의 쉼표 여 생략 된 인수의 위치를 표시할 수 있습니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>함수.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
     [!code-vb[VbVbcnProcedures #&34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     앞의 예제에 표시 될 메시지 문자열은 필요한 첫 번째 인수를 제공 합니다. 메시지 상자에 표시할 단추를 지정 하는 선택적 두 번째 매개 변수에 대 한 인수를 생략 합니다. 호출에 값을 제공 하지 않는 때문에 `MsgBox` 기본값을 사용 하 여 `MsgBoxStyle.OKOnly`만 표시 되는 **확인** 단추입니다.  
  
     인수 목록에 두 번째 쉼표는 생략 두 번째 인수의 위치를 표시 하 고 마지막 문자열의 세 번째 선택적 매개 변수에 전달 됩니다 `MsgBox`, 제목 표시줄에 표시할 텍스트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Sub 프로시저](./sub-procedures.md)   
 [Function 프로시저](./function-procedures.md)   
 [속성 프로시저](./property-procedures.md)   
 [연산자 프로시저](./operator-procedures.md)   
 [방법: 프로시저에 대 한 매개 변수를 정의 합니다.](./how-to-define-a-parameter-for-a-procedure.md)   
 [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)   
 [재귀 프로시저](./recursive-procedures.md)   
 [프로시저 오버 로드](./procedure-overloading.md)   
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
