---
title: "Considerations in Overloading Procedures (Visual Basic) | Microsoft Docs"
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
  - "signatures, ParamArray arguments"
  - "ParamArray keyword, parameter arrays"
  - "ParamArray keyword, arguments and signatures"
  - "function overloading, implicit overloads for ParamArray"
  - "ParamArray keyword, signatures"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], parameter arrays"
  - "procedures, overloading"
  - "parameters, lists"
  - "function overloading, typeless programming"
  - "typeless programming"
  - "function overloading, restrictions"
  - "arguments [Visual Basic], optional"
  - "optional arguments, overloading"
  - "signatures, procedure"
  - "parameter lists"
  - "parameter arrays, overloading arguments"
  - "Visual Basic code, parameter lists"
  - "procedure overloading, considerations"
  - "Option Explicit statement"
  - "restrictions, overloading procedures"
  - "procedures, parameter lists"
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Considerations in Overloading Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저를 오버로드할 때는 오버로드된 각 버전에 서로 다른 *시그니처*를 사용해야 합니다.  이는 일반적으로 각 버전에서 서로 다른 매개 변수 목록을 지정해야 한다는 것을 의미합니다.  자세한 내용은 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)에서 "서로 다른 시그니처"를 참조하십시오.  
  
 시그니처가 다르면 `Sub` 프로시저로 `Function` 프로시저를 오버로드할 수 있고 그 반대로 오버로드할 수도 있습니다.  하나는 반환 값을 가지고 다른 하나는 반환 값을 가지지 않으므로 이 두 오버로드는 다를 수 없습니다.  
  
 프로시저를 오버로드할 때와 같은 방식 및 제한 사항에 따라서 속성을 오버로드할 수 있습니다.  그러나 속성으로 프로시저를 오버로드하거나 프로시저로 속성을 오버로드할 수는 없습니다.  
  
## 오버로드된 버전의 대체 방법  
 경우에 따라서는 오버로드된 버전을 대신하는 다른 방법을 사용할 수 있습니다. 특히 인수의 존재 여부가 선택적이거나 인수의 수가 가변적일 경우가 이에 해당합니다.  
  
 선택적 인수가 모든 언어에서 지원되는 것은 아니며 매개 변수 배열이 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]으로 제한되어 있다는 점에 주의합니다.  여러 다른 언어로 작성된 코드에서 호출되는 프로시저를 작성하는 경우에는 오버로드된 버전이 가장 뛰어난 유연성을 제공합니다.  
  
### 오버로드 및 선택적 인수  
 호출 코드에서 하나 이상의 인수를 선택적으로 제공하거나 생략할 수 있는 경우 오버로드된 여러 버전을 정의하거나 선택적 매개 변수를 사용할 수 있습니다.  
  
#### 오버로드된 버전을 사용하는 경우  
 다음 경우에 일련의 오버로드된 버전을 정의해 볼 수 있습니다.  
  
-   호출 코드에서 선택적 인수를 제공하는지 여부에 따라서 프로시저 코드의 논리가 크게 달라지는 경우  
  
-   호출 코드에서 선택적 인수를 제공했는지 여부를 프로시저 코드가 안정적으로 테스트할 수 없는 경우.  예를 들어, 호출 코드에서 제공되지 않을 기본값에 대한 대체 값이 없는 경우가 이에 해당합니다.  
  
#### 선택적 매개 변수를 사용하는 경우  
 다음 경우에 하나 이상의 선택적 매개 변수를 사용할 수 있습니다.  
  
-   호출 코드에서 선택적 인수를 제공하지 않는 경우에 매개 변수를 기본값으로 설정하는 작업만 필요한 경우.  이러한 경우 하나 이상의 `Optional` 매개 변수로 단일 버전을 정의하면 프로시저 코드는 덜 복잡해질 수 있습니다.  
  
 자세한 내용은 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)를 참조하십시오.  
  
### 오버로드 및 ParamArray  
 호출 코드에서 여러 가지 인수를 전달할 수 있는 경우 오버로드된 여러 버전을 정의하거나 매개 변수 배열을 사용할 수 있습니다.  
  
#### 오버로드된 버전을 사용하는 경우  
 다음 경우에 일련의 오버로드된 버전을 정의해 볼 수 있습니다.  
  
-   호출 코드에서 항상 적은 수의 값만 매개 변수 배열에 전달한다는 것이 확실한 경우  
  
-   호출 코드에서 전달하는 값 수에 따라 프로시저 코드의 논리가 크게 달라지는 경우  
  
-   호출 코드에서 다른 데이터 형식의 값을 전달할 수 있는 경우  
  
#### 매개 변수 배열을 사용하는 경우  
 다음 경우에는 `ParamArray` 매개 변수를 사용하는 것이 좋습니다.  
  
-   호출 코드에서 매개 변수 배열에 전달할 수 있는 값 수를 예측할 수 없으며 많은 수의 값이 매개 변수 배열에 전달될 수 있는 경우  
  
-   호출 코드에서 전달하는 모든 값에서 프로시저 논리가 반복되어 본질적으로 모든 값에 대해 동일한 작업을 수행하는 경우  
  
 자세한 내용은 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)을 참조하십시오.  
  
## 선택적 매개 변수의 암시적 오버로드  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수가 있는 프로시저는 오버로드된 두 개의 프로시저\(선택적 매개 변수가 있는 것과 없는 것\)와 같습니다.  둘 중 하나에 해당하는 매개 변수 목록을 사용하는 이러한 프로시저는 오버로드할 수 없습니다.  다음은 이에 대한 선언입니다.  
  
 [!code-vb[VbVbcnProcedures#58](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_3.vb)]  
  
 선택적 매개 변수가 둘 이상인 프로시저에는 앞 예제와 유사한 논리로 인해 발생한 암시적 오버로드 집합이 존재합니다.  
  
## ParamArray 매개 변수의 암시적 오버로드  
 컴파일러에서는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수가 있는 프로시저에 무제한의 오버로드가 포함될 수 있다고 간주합니다. 이 오버로드들은 호출 코드에서 매개 변수 배열에 전달하는 내용에 따라 다음과 같이 서로 다릅니다.  
  
-   호출 코드에서 `ParamArray`에 인수를 제공하지 않을 경우 하나의 오버로드  
  
-   호출 코드에서 `ParamArray` 요소 형식의 1차원 배열을 제공할 경우 하나의 오버로드  
  
-   각각의 양의 정수에 대해 호출 코드에서 `ParamArray` 요소 형식에 해당 개수의 인수를 제공할 경우 하나의 오버로드  
  
 다음 선언은 이러한 암시적 오버로드를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#68](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_5.vb)]  
  
 매개 변수 배열에 1차원 배열을 사용하는 매개 변수 목록으로는 그러한 프로시저를 오버로드할 수 없습니다.  그러나 다른 암시적 오버로드의 시그니처를 사용할 수는 있습니다.  다음은 이에 대한 선언입니다.  
  
 [!code-vb[VbVbcnProcedures#71](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_6.vb)]  
  
## 오버로딩을 대체하는 관대한 형식의 프로그래밍  
 호출 코드에서 매개 변수에 서로 다른 데이터 형식을 전달할 수 있도록 하려면 대안은 관대 한 형식의 프로그래밍입니다.  [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [\/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용하여 형식 검사 스위치를 `Off`로 설정할 수 있습니다.  그런 다음에는 매개 변수의 데이터 형식을 선언할 필요가 없습니다.  그러나 오버로딩에 비해 무형식 프로그래밍은 다음과 같은 단점을 가지고 있습니다.  
  
-   관대한 형식의 프로그래밍을 사용한 실행 코드는 효율성이 떨어집니다.  
  
-   전달될 수 있는 모든 데이터 형식에 대해 프로시저를 테스트해야 합니다.  
  
-   호출 코드에서 프로시저가 지원하지 않는 데이터 형식을 전달하는 경우 컴파일러에서 오류를 알리지 못합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)