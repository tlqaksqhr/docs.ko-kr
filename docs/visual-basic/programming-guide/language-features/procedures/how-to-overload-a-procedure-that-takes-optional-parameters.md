---
title: "How to: Overload a Procedure that Takes Optional Parameters (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, parameters"
  - "procedure overloading, optional parameters"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedure parameters"
  - "procedures, overloading"
  - "procedures, multiple versions"
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저에 하나 이상의 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수가 있을 경우 암시적 오버로드와 일치하는 오버로드된 버전을 정의할 수 없습니다.  자세한 내용은 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)에서 "선택적 매개 변수의 암시적 오버로드"를 참조하십시오.  
  
## 단일 선택적 매개 변수  
  
#### 하나의 선택적 매개 변수를 가지는 프로시저를 오버로드하려면  
  
1.  매개 변수 목록에서 선택적 매개 변수를 포함하는 `Sub` 또는 `Function` 선언문을 작성합니다.  이 오버로드된 버전에서 `Optional` 키워드를 사용하지 마십시오.  
  
2.  `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 사용합니다.  
  
3.  호출 코드에서 선택적 인수를 제공할 경우 실행해야 하는 프로시저 코드를 작성합니다.  
  
4.  프로시저를 상황에 맞게 `End Sub` 또는 `End Function` 문으로 종료합니다.  
  
5.  매개 변수 목록에 선택적 매개 변수를 포함하지 않는다는 점을 제외하고 첫 번째 선언과 동일한 두 번째 선언문을 작성합니다.  
  
6.  호출 코드에서 선택적 인수를 제공하지 않을 경우 실행해야 하는 프로시저 코드를 작성합니다.  프로시저를 상황에 맞게 `End Sub` 또는 `End Function` 문으로 종료합니다.  
  
     다음 예제에서는 선택적 매개 변수와 함께 정의된 프로시저, 두 개의 오버로드된 프로시저의 동등한 집합, 유효한 오버로드된 버전과 유효하지 않은 오버로드된 버전의 예를 보여 줍니다.  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## 여러 선택적 매개 변수  
 둘 이상의 선택적 매개 변수를 가진 프로시저의 경우 일반적으로 세 개 이상의 오버로드된 버전이 필요합니다.  예를 들어, 두 개의 선택적 매개 변수가 존재하고 호출 코드가 매개 변수를 서로 독립적으로 제공하거나 생략할 수 있는 경우 네 개의 오버로드된 버전\(제공된 인수의 가능한 각 조합별로 하나씩\)이 필요합니다.  
  
 선택적 매개 변수의 수가 증가하면 오버로드의 복잡도가 증가합니다.  제공된 인수의 일부 조합이 허용되지 않는 경우가 아니라면 N개의 선택적 매개 변수에 대해 2 ^ N개의 오버로드된 버전이 필요합니다.  프로시저의 특성에 따라 논리를 분명히 하기 위해서 오버로드된 모든 버전을 정의하기 위한 수고를 들여야 할 수 있습니다.  
  
#### 둘 이상의 선택적 매개 변수를 가진 프로시저를 오버로드하려면  
  
1.  제공된 선택적 인수의 조합 중에서 프로시저의 논리에 허용되는 조합을 결정합니다.  하나의 선택적 매개 변수가 다른 선택적 매개 변수에 의존할 경우 허용되지 않는 인수 조합이 발생할 수 있습니다.  예를 들어, 하나의 매개 변수에서 배우자의 이름이 허용되고 다른 매개 변수에서 배우자의 나이가 허용될 경우 나이를 제공하지만 이름을 생략하는 인수 조합은 허용되지 않습니다.  
  
2.  제공된 선택적 인수의 허용되는 각 조합에 대해 해당 매개 변수 목록을 정의하는 `Sub` 또는 `Function` 선언문을 작성합니다.  `Optional` 키워드는 사용하지 마십시오.  
  
3.  모든 선언에서 `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 지정합니다.  
  
4.  각 선언 다음에는 호출 코드가 해당 선언의 매개 변수 목록에 해당하는 인수 목록을 제공할 때 실행되어야 하는 프로시저 코드를 작성합니다.  
  
5.  각 프로시저를 상황에 맞게 `End Sub` 또는 `End Function` 문으로 종료합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)