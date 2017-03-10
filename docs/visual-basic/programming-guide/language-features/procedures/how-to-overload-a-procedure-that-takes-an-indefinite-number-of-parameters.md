---
title: "How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic) | Microsoft Docs"
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
  - "procedure overloading, indefinite number of parameters"
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "procedure parameters"
  - "procedures, overloading"
  - "procedures, multiple versions"
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저에 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수가 있으면 매개 변수 배열에 1차원 배열을 사용하는 오버로드된 버전을 정의할 수 없습니다.  자세한 내용은 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)의 "ParamArray 매개 변수의 암시적 오버로드"를 참조하십시오.  
  
### 여러 가지 매개 변수를 사용하는 프로시저를 오버로드하려면  
  
1.  프로시저와 호출 코드 논리에는 `ParamArray` 매개 변수보다 오버로드된 버전이 더 유용한 것을 확인합니다.  [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)의 "오버로드 및 ParamArray"를 참조하십시오.  
  
2.  제공된 값 중 프로시저에서 매개 변수 목록의 변수 부분에 적용해야 할 숫자를 결정합니다.  값을 적용하지 않거나 단일 1차원 배열을 적용할 수 있습니다.  
  
3.  제공된 값의 수가 적절한 경우 해당 매개 변수 목록을 정의하는 `Sub` 또는 `Function` 선언문을 작성합니다.  이 오버로드된 버전에는 `Optional` 또는 `ParamArray` 키워드를 사용하지 마십시오.  
  
4.  모든 선언에서 `Sub` 또는 `Function` 키워드 앞에 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 지정합니다.  
  
5.  각각의 선언이 완료되면 호출 코드에서 해당 선언의 매개 변수 목록에 해당하는 값을 제공할 경우 실행할 프로시저 코드를 작성합니다.  
  
6.  각 프로시저를 상황에 맞게 `End Sub` 또는 `End Function` 문으로 종료합니다.  
  
## 예제  
 다음 예제에서는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수를 사용하여 정의한 프로시저를 보여 준 다음 오버로드된 프로시저의 해당 집합을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#69](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-overload-a-proced_0_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-overload-a-proced_0_2.vb)]  
  
 매개 변수 배열에 1차원 배열을 사용하는 매개 변수 목록으로는 그러한 프로시저를 오버로드할 수 없습니다.  그러나 다른 암시적 오버로드의 시그니처를 사용할 수는 있습니다.  다음은 이에 대한 선언입니다.  
  
 [!code-vb[VbVbcnProcedures#71](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-overload-a-proced_0_3.vb)]  
  
 오버로드된 버전의 코드에서는 호출 코드에서 `ParamArray` 매개 변수에 하나 이상의 값을 제공했는지 여부나 제공했다면 몇 개를 제공했는지를 테스트하지 않아도 됩니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 호출 인수 목록과 일치하는 버전으로 제어가 전달됩니다.  
  
## 코드 컴파일  
 `ParamArray` 매개 변수를 사용하는 프로시저는 오버로드된 버전 집합과 동일하므로, 이러한 암시적 오버로드에 해당하는 매개 변수 목록으로는 그러한 프로시저를 오버로드할 수 없습니다.  자세한 내용은 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)을 참조하십시오.  
  
## .NET Framework 보안  
 무제한으로 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량에 오버런이 발생할 위험이 있습니다.  매개 변수 배열을 받는 경우에는 호출 코드로부터 받은 배열의 길이를 테스트해야 합니다. 이때 길이가 너무 길어서 해당 배열을 응용 프로그램에 사용할 수 없는 경우에는 적절한 조치를 취합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)