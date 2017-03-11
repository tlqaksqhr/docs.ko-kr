---
title: "Overload Resolution (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, procedures"
  - "overload resolution"
  - "procedures, overloading"
  - "procedures, calling"
  - "procedure overloading, overload resolution"
  - "signatures, procedure"
  - "overloads, resolution"
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Overload Resolution (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서 여러 오버로드 버전으로 정의된 프로시저에 대한 호출을 발견할 경우 어떤 오버로드를 호출할지 결정해야 합니다.  이러한 결정은 다음 단계를 수행하여 결정됩니다.  
  
1.  **액세스 가능성.** 호출 코드의 호출을 금지하는 액세스 수준의 오버로드를 모두 제거합니다.  
  
2.  **매개 변수의 개수.** 호출에서 제공하는 것과 다른 개수의 매개 변수를 정의하는 오버로드를 모두 제거합니다.  
  
3.  **매개 변수 데이터 형식.** 확장 메서드에 대한 기본 설정 인스턴스 메서드를 제공합니다.  프로시저 호출과 일치시키기 위해 확대 변환만 필요한 인스턴스 메서드를 찾은 경우 모든 확장 메서드를 삭제하고 해당 인스턴스 메서드 후보만 검토합니다.  이러한 인스턴스 메서드가 없으면 인스턴스와 확장 메서드를 모두 검토합니다.  
  
     이 단계에서는 호출 인수의 데이터 형식을 오버로드에 정의된 매개 변수 형식으로 변환할 수 없는 오버로드를 모두 제거합니다.  
  
4.  **축소 변환.** 호출 인수 형식보다 정의된 매개 변수 형식의 범위가 좁은 오버로드를 모두 제거합니다.  이때 형식 검사 스위치\([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\)가 `On`인지 `Off`인지는 문제가 되지 않습니다.  
  
5.  **최소 확대.** 남은 오버로드를 쌍으로 검토합니다.  각 쌍에 대해, 정의된 매개 변수의 데이터 형식을 비교합니다.  한 오버로드에 사용된 모든 형식이 다른 오버로드에 사용된 형식으로 확장될 경우 나중의 오버로드를 제거합니다.  즉, 컴파일러는 가장 적게 확장되는 오버로드만 남깁니다.  
  
6.  **단일 후보.** 오버로드가 하나만 남을 때까지 계속 오버로드를 쌍으로 검토한 후 해당 호출을 마지막에 남아 있는 오버로드로 확인합니다.  컴파일러에서는 오버로드를 하나의 후보로 줄일 수 없는 경우 오류를 생성합니다.  
  
 다음 그림에서는 호출할 오버로드 버전 집합을 결정하는 프로세스를 보여 줍니다.  
  
 ![오버로드 확인 프로세스의 흐름도](../../../../visual-basic/programming-guide/language-features/procedures/media/overloadres.gif "OverloadRes")  
오버로드 버전에서 확인  
  
 다음 예제는 오버로드 확인 프로세스를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#62](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/overload-resolution_2.vb)]  
  
 첫 번째 호출에서는 첫 번째 인수\(`Short`\)가 해당 매개 변수의 형식\(`Byte`\)으로 축소되므로 컴파일러에서 첫 번째 오버로드를 제거합니다.  그런 다음 두 번째 오버로드의 각 인수 형식\(`Short`와 `Single`\)이 세 번째 오버로드의 해당 형식\(`Integer`와 `Single`\)으로 확대되므로 세 번째 오버로드를 제거합니다.  두 번째 오버로드는 덜 확대해도 되므로 컴파일러에서 이 오버로드를 호출에 사용합니다.  
  
 두 번째 호출에서는 컴파일러가 축소를 기준으로 오버로드를 제거할 수 없습니다.  인수 형식을 덜 확대해도 두 번째 오버로드를 호출할 수 있으므로 첫 번째 호출의 경우와 같은 이유로 세 번째 오버로드를 제거합니다.  그러나 컴파일러에서 첫 번째와 두 번째 오버로드 사이를 확인할 수 없습니다.  각 오버로드에는 다른 오버로드의 해당 형식으로 확대되도록 정의된 매개 변수 형식\(`Byte`에서 `Short`로, `Single`에서 `Double`로\)이 하나씩 있습니다.  따라서 컴파일러에서 오버로드 확인 오류를 생성합니다.  
  
## 오버로드된 Optional 및 ParamArray 인수  
 마지막 매개 변수가 각각 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)로 선언된다는 점만 제외하고 프로시저에서 두 오버로드의 시그니처가 같은 경우 컴파일러는 해당 프로시저에 대한 호출을 다음과 같이 확인합니다.  
  
|||  
|-|-|  
|호출에서 마지막 인수를 다음과 같이 제공합니다.|컴파일러에서는 마지막 인수를 다음과 같이 선언하는 오버로드로 호출을 확인합니다.|  
|값 없음\(인수 생략\)|`Optional`|  
|단일 값|`Optional`|  
|쉼표로 구분된 목록에 있는 둘 이상의 값|`ParamArray`|  
|임의 길이의 배열\(빈 배열 포함\)|`ParamArray`|  
  
## 참고 항목  
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Considerations in Overloading Procedures](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)