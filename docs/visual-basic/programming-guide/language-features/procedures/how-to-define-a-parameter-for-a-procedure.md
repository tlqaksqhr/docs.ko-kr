---
title: "방법: 프로시저 (Visual Basic)에 대 한 매개 변수를 정의 합니다. | Microsoft 문서"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 9fb9ad244499039c1768ff97f071168e0a0842e4
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>방법: 프로시저의 매개 변수 정의(Visual Basic)
A *매개 변수* 호출 코드를 호출할 때 프로시저에 값을 전달할 수 있습니다. 동일한 방식으로 변수를 선언 하면 해당 이름 및 데이터 형식을 지정 하는 프로시저에 대 한 각 매개 변수를 선언 합니다. 또한 전달 메커니즘을 지정 및 매개 변수는 선택 사항입니다.  
  
 자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.  
  
### <a name="to-define-a-procedure-parameter"></a>프로시저 매개 변수를 정의 하려면  
  
1.  프로시저 선언에서 매개 변수 이름이 다른 매개 변수에서 쉼표로 구분 되는 프로시저의 매개 변수 목록에 추가 합니다.  
  
2.  매개 변수의 데이터 형식을 결정 합니다.  
  
3.  매개 변수 이름 뒤에 `As` 데이터 형식을 지정 하는 절.  
  
4.  매개 변수에 대해 원하는 전달 메커니즘을 결정 합니다. 일반적으로 프로시저 호출 코드에서 해당 값을 변경할 수 있게 되기를 원하지 않는 한 값으로 매개 변수를 전달 합니다.  
  
5.  매개 변수 이름 앞에 야 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 전달 메커니즘을 지정 합니다. 자세한 내용은 참조 [차이 사이 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.  
  
6.  경우에 매개 변수는 선택 사항, 전달 메커니즘 앞에 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 등호로 매개 변수 데이터 형식에 따라 (`=`) 및 기본 값입니다.  
  
     개요를 정의 하는 다음 예제는 `Sub` 세 개의 매개 변수가 있는 프로시저입니다. 처음 두 개의 필수 필드 이며 세 번째는 선택 사항입니다. 매개 변수 선언 매개 변수 목록에 쉼표로 구분 됩니다.  
  
     [!code-vb[VbVbcnProcedures #&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     첫 번째 매개 변수가 허용는 `customer` 개체 및 `updateCustomer` 에 전달 된 변수를 직접 업데이트할 수 `c` 인수 전달 되기 때문에 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다. 프로시저 전달 되므로 마지막 두 인수 값을 변경할 수 없습니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.  
  
     호출 코드에 대 한 값을 제공 하지 않는 경우는 `level` 매개 변수를 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 기본값인 0으로 설정 합니다.  
  
     전환 하는 형식 검사 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `Off`, `As` 매개 변수를 정의 하는 경우 절은 선택 사항입니다. 그러나 하나의 매개 변수를 사용 하는 경우는 `As` 절 모두에 사용 해야 합니다. 형식 검사 스위치가 경우 `On`, `As` 절은 모든 매개 변수 정의에 필요 합니다.  
  
     모든 프로그래밍 요소에 대 한 데이터 형식 지정 이라고 *강력한 형식 지정*합니다. 설정한 경우 `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 강력한 형식 지정을 적용 합니다. 이 것이 좋습니다 이유는 다음과 같습니다.  
  
    -   변수 및 매개 변수에 대 한 IntelliSense 지원도를 수 있습니다. 이렇게 하면 코드의 입력 속성 및 다른 멤버를 볼 수 있습니다.  
  
    -   컴파일러를에 형식 검사를 수행할 수 있습니다. 이렇게 하면 catch 문을 런타임에 오버플로와 같은 오류로 인해 실패할 수 있습니다. 또한 지원 하지 않는 개체에 메서드 호출을 찾아냅니다.  
  
    -   그 결과, 코드의 실행이 빨라집니다. 이 대 한 한 가지 이유 하는 경우 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않으면는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 할당은 `Object` 유형입니다. 컴파일된 코드 사이 변환 해야 할 수 `Object` 및 다른 데이터 형식의 경우 성능이 떨어집니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [Function 프로시저](./function-procedures.md)   
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)   
 [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)   
 [재귀 프로시저](./recursive-procedures.md)   
 [프로시저 오버 로드](./procedure-overloading.md)   
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
