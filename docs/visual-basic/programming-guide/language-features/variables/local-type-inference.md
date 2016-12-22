---
title: "Local Type Inference (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "local type inference"
  - "vb.TypeInfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Option Infer statement"
  - "local type inference [Visual Basic]"
  - "implicitly-typed local variables [Visual Basic]"
  - "variables [Visual Basic], type inference"
  - "inference [Visual Basic]"
  - "type inference [Visual Basic]"
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
caps.handback.revision: 43
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Local Type Inference (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Visual Basic 컴파일러는 *형식 유추*를 사용하여 `As` 절 없이 선언된 지역 변수의 데이터 형식을 결정합니다.  컴파일러는 초기화 식의 형식에서 변수 형식을 유추합니다.  따라서 다음 예제와 같이 형식을 명시하지 않고 변수를 선언할 수 있습니다. 선언 결과로 `num1`과 `num2`는 모두 정수로 강력하게 형식화되어 있습니다.  
  
 [!CODE [VbVbalrTypeInference#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTypeInference#1)]  
  
> [!NOTE]
>  앞의 예제에서 `num2`를 `Integer` 형식으로 만들지 않으려면 `Dim num3 As Object = 3` 또는 `Dim num4 As Double = 3` 같은 선언을 사용하여 다른 형식을 지정하면 됩니다.  
  
 지역 형식 유추는 프로시저 수준에서 적용됩니다.  모듈 수준, 즉 클래스, 구조체, 모듈 또는 인터페이스 내에서 변수를 선언하는 데는 사용할 수 없지만 프로시저 또는 블록 내에서는 사용할 수 있습니다.  앞의 예제에서 `num2`가 프로시저의 지역 변수가 아니라 클래스의 필드였다면 `Option Strict` on의 경우 선언에서 오류가 발생하고, `Option Strict` off의 경우 `num2`를 `Object`로 분류했을 것입니다.  마찬가지로 지역 형식 참조는 `Static`으로 선언된 프로시저 수준 변수에 적용되지 않습니다.  
  
## 형식 유추와런타임에 바인딩 비교  
 형식 유추를 사용하는 코드는 런타임에 바인딩을 사용하는 코드와 비슷합니다.  그러나 형식 유추는 변수를 `Object`로 두는 대신 강력한 형식으로 만듭니다.  컴파일러는 변수의 이니셜라이저를 사용하여 초기 바인딩 코드를 만들기 위한 변수의 형식을 컴파일 타임에 결정합니다.  앞의 예제에서 `num2`는 `num1`과 마찬가지로 `Integer` 형식으로 지정되었습니다.  
  
 초기 바인딩 변수의 동작은 런타임에만 형식을 알 수 있는 런타임에 바인딩된 변수의 동작과 다릅니다.  형식을 초기에 알면 컴파일러가 실행 이전에 문제를 식별하고, 메모리를 정확하게 할당하고, 기타 최적화를 수행할 수 있습니다.  초기 바인딩은 Visual Basic IDE\(통합 개발 환경\)에서 개체의 멤버에 대한 IntelliSense 도움말도 제공할 수 있도록 합니다.  또한 초기 바인딩은 성능 때문에 선호됩니다.  런타임에 바인딩된 변수에 저장된 모든 데이터는 `Object` 형식으로 래핑되어야 하고, 런타임에 이 형식의 멤버에 액세스하면 프로그램이 느려지기 때문입니다.  
  
## 예제  
 형식 유추는 `As` 절 없이 선언된 지역 변수가 초기화될 때 발생합니다.  컴파일러는 할당된 초기 값의 형식을 변수의 형식으로 사용합니다.  예를 들어, 다음 코드 줄은 각각 `String` 형식의 변수를 선언합니다.  
  
 [!CODE [VbVbalrTypeInference#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTypeInference#2)]  
  
 다음 코드에서는 정수 배열을 만들기 위한 두 가지의 동일한 방법을 보여 줍니다.  
  
 [!CODE [VbVbalrTypeInference#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTypeInference#3)]  
  
 형식 유추를 사용하여 편리하게 루프 제어 변수의 형식을 결정할 수 있습니다.  다음 코드에서 컴파일러는 앞의 예제의 `someNumbers2`가 정수 배열이므로 `number`가 `Integer`라고 유추합니다.  
  
 [!CODE [VbVbalrTypeInference#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTypeInference#4)]  
  
 지역 형식 유추는 다음 예제와 같이 `Using` 문에서 리소스 이름의 형식을 설정하는 데 사용될 수 있습니다.  
  
 [!CODE [VbVbalrTypeInference#7](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTypeInference#7)]  
  
 변수의 형식은 다음 예제와 같이 함수의 반환 값에서 유추될 수도 있습니다.  `Process.GetProcesses`가 프로세스 배열을 반환하므로 `pList1`과 `pList2`는 모두 프로세스 배열입니다.  
  
 [!CODE [VbVbalrTypeInference#5](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrTypeInference#5)]  
  
## Option Infer  
 `Option Infer`특정 파일에서 지역 형식 유추가 허용 되는지 여부를 지정할 수 있습니다.  옵션을 허용하거나 차단하려면 파일의 시작 부분에 다음 문 중 하나를 입력합니다.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 코드에서 `Option Infer`에 대한 값을 지정하지 않는 경우 컴파일러 기본값은 `Option Infer On`입니다.  [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] 이전에서 업그레이드된 프로젝트의 경우 컴파일러 기본값은 `Option Infer Off`입니다.  
  
 파일에서 `Option Infer`에 대해 설정한 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우 파일의 값이 우선 순위를 갖습니다.  
  
 자세한 내용은 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)을 참조하십시오.  
  
## 제한  
 형식 유추는 정적이 아닌 지역 변수에만 사용될 수 있으며 클래스 필드, 속성 또는 함수의 형식을 결정하는 데에는 사용될 수 없습니다.  
  
## 참고 항목  
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next 문](../../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [\/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)