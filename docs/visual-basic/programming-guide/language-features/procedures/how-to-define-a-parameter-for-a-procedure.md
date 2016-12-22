---
title: "How to: Define a Parameter for a Procedure (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedure parameters, defining data types for"
  - "procedures, parameters"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedure parameters, defining"
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Define a Parameter for a Procedure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*매개 변수*를 사용하면 호출 코드에서 프로시저를 호출할 때 프로시저에 값을 전달할 수 있습니다.  프로시저의 각 매개 변수는 변수를 선언할 때와 같이 매개 변수 이름과 데이터 형식을 지정하여 선언합니다.  매개 변수를 선택적 요소로 할 것인지 여부와 전달 메커니즘도 지정할 수 있습니다.  
  
 자세한 내용은 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)를 참조하십시오.  
  
### 프로시저 매개 변수를 정의하려면  
  
1.  프로시저 선언에서 매개 변수 이름을 프로시저의 매개 변수 목록에 추가합니다. 쉼표를 사용하여 다른 매개 변수와 구분합니다.  
  
2.  매개 변수의 데이터 형식을 결정합니다.  
  
3.  매개 변수 이름 다음에 `As` 절을 사용하여 데이터 형식을 지정합니다.  
  
4.  매개 변수에 사용할 전달 메커니즘을 결정합니다.  프로시저에서 호출 코드의 해당 값을 변경할 수 있게 하려는 경우가 아니라면 일반적으로 매개 변수를 값으로 전달합니다.  
  
5.  매개 변수 이름 앞에 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)를 사용하여 전달 메커니즘을 지정합니다.  자세한 내용은 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)을 참조하십시오.  
  
6.  매개 변수가 선택적 요소이면 전달 메커니즘 앞에 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)을 사용하고 매개 변수 데이터 형식 뒤에 등호\(`=`\)와 기본값을 사용합니다.  
  
     다음 예제에서는 세 개의 매개 변수를 가진 `Sub` 프로시저의 개요를 정의합니다.  처음 두 개는 필수적 요소이고 세 번째는 선택적 요소입니다.  매개 변수 목록에서 매개 변수 선언은 쉼표로 구분됩니다.  
  
     [!code-vb[VbVbcnProcedures#33](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     첫 번째 매개 변수는  `customer`  개체를 받아들이고 인수는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 전달되기 때문에 `updateCustomer`는 `c`에 전달된 변수를 직접 업데이트할 수 있습니다.  마지막 두 인수는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 전달되므로 프로시저에서 이러한 인수의 값을 변경할 수 없습니다.  
  
     호출 코드에서  `level` 매개 변수에 대한 값을 제공하지 않을 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 해당 값을 기본값인 0으로 설정합니다.  
  
     형식 검사 스위치\([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\)가 `Off`이면 매개 변수를 정의할 때 `As` 절은 선택적 요소가 됩니다.  그러나 특정 매개 변수에 `As` 절을 사용할 경우 모든 매개 변수에서 이 절을 사용해야 합니다.  형식 검사 스위치가 `On`이면 모든 매개 변수 정의에서 `As` 절이 필요합니다.  
  
     모든 프로그래밍 요소에 대해 데이터 형식을 지정하는 것을 *강력한 형식화*라고 합니다.  `Option Strict On`을 설정하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 강력한 형식화를 적용합니다.  다음과 같은 이유 때문에 이 설정을 사용하는 것이 적극 권장됩니다.  
  
    -   변수와 매개 변수에 대해 IntelliSense 지원을 사용할 수 있습니다.  이를 사용하면 코드에서 입력할 때 해당 속성과 다른 멤버를 볼 수 있습니다.  
  
    -   컴파일러에서 형식 검사를 수행하여  오버플로와 같은 오류로 인해 런타임에서 실패할 가능성이 있는 문을 찾아낼 수 있습니다.  또한 지원되지 않는 개체에 대한 메서드 호출을 찾아냅니다.  
  
    -   코드 실행이 빨라집니다.  그 이유 중 하나는 프로그래밍 요소에 데이터 형식이 지정되지 않을 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 `Object` 형식을 할당하기 때문입니다.  컴파일된 코드를 `Object` 및 다른 데이터 형식 사이에서 변환해야 할 수 있으며 이 경우에 성능이 저하됩니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Recursive Procedures](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [개체 지향 프로그래밍](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)