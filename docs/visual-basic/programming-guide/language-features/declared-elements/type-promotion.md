---
title: "Type Promotion (Visual Basic) | Microsoft Docs"
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
  - "declared elements, scope"
  - "visibility, declared elements"
  - "Partial keyword, unexpected results with type promotion"
  - "scope, declared elements"
  - "scope, Visual Basic"
  - "type promotion"
  - "declared elements, visibility"
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type Promotion (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

모듈에 프로그래밍 요소를 선언하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 해당 요소의 범위를 모듈이 들어 있는 네임스페이스로 승격합니다.  이를 *형식 승격*이라고 합니다.  
  
 다음 예제에서는 모듈의 기본 정의와 해당 모듈의 두 가지 멤버를 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 `projModule` 내에서 모듈 수준에 선언된 프로그래밍 요소는 `projNamespace`로 승격됩니다.  위의 예제에서 `basicEnum` 및 `innerClass`는 승격되지만 `numberSub`는 모듈 수준에 선언되지 않았으므로 승격되지 않습니다.  
  
## 형식 승격의 효과  
 형식을 승격하면 한정 문자열에 모듈 이름을 포함하지 않아도 됩니다.  다음 예제에서는 위 예제의 프로시저를 두 번 호출합니다.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 이 예제의 첫 번째 호출에서는 완전한 한정 문자열을 사용합니다.  그러나 형식이 승격되었으므로 한정 문자열은 필요하지 않습니다.  또한 두 번째 호출에서는 한정 문자열에 `projModule`을 포함하지 않고 모듈의 멤버에 액세스합니다.  
  
## 형식 승격의 무효화  
 네임스페이스에 모듈 멤버와 동일한 이름의 멤버가 이미 있으면 해당 모듈 멤버에 대한 형식 승격이 무효화됩니다.  다음 예제에서는 동일한 네임스페이스에 있는 열거형과 모듈의 기본 정의를 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 위 예제에서는 네임스페이스 수준에 동일한 이름의 열거형이 이미 있기 때문에 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 `abc` 클래스를 `thisNameSpace`로 승격할 수 없습니다.  `abcSub`에 액세스하려면 정규화 문자열 `thisNamespace.thisModule.abc.abcSub`를 사용해야 합니다.  그러나 `xyz` 클래스는 여전히 승격되므로 보다 짧은 한정 문자열 `thisNamespace.xyz.xyzSub`를 사용하여 `xyzSub`에 액세스할 수 있습니다.  
  
### 부분 형식\(Partial Type\)에 대한 형식 승격 무효화  
 모듈 내의 클래스나 구조에서 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) 키워드를 사용하는 경우 네임스페이스에 동일한 이름의 멤버가 있는지 여부에 상관없이 해당 클래스나 구조에 대한 형식 승격이 자동으로 무효화됩니다.  그러나 모듈 내의 다른 요소에 대해서는 형식을 승격할 수 있습니다.  
  
 **결과.** 부분 정의에 대한 형식 승격이 무효화되면 예기치 않은 결과나 컴파일러 오류가 발생할 수 있습니다.  다음 예제에서는 클래스의 기본 부분 정의를 보여 주며, 이 중 하나는 모듈 내에 있습니다.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 위 예제에서 개발자는 컴파일러에서 `sampleClass`의 두 가지 부분 정의를 병합할 것이라고 기대할 수 있습니다.  그러나 컴파일러에서는 `sampleModule` 내의 부분 정의에 대한 승격을 고려하지 않습니다.  따라서 이름이 `sampleClass`로 같지만 한정 경로는 서로 다른 두 개의 개별 클래스를 컴파일하려고 시도합니다.  
  
 컴파일러에서는 정규화된 경로가 동일할 때만 부분 정의를 병합합니다.  
  
## 권장 사항  
 다음은 바람직한 프로그래밍을 위한 권장 사항입니다.  
  
-   **고유 이름.** 프로그래밍 요소의 이름을 제어할 수 있으면 모든 요소에 항상 고유 이름을 사용하는 것이 좋습니다.  동일한 이름을 사용하려면 추가 한정이 필요하며 이 경우 코드가 복잡해질 수 있습니다.  또한 사소한 오류와 예기치 않은 결과가 발생할 수 있습니다.  
  
-   **정규화.** 동일한 네임스페이스의 모듈 및 기타 요소를 사용하여 작업할 때는 항상 모든 프로그래밍 요소를 정규화하는 것이 가장 안전합니다.  모듈 멤버를 정규화하지 않은 경우 해당 멤버에 대해 형식 승격이 무효화되면 실수로 다른 프로그래밍 요소에 액세스하게 될 수 있습니다.  
  
## 참고 항목  
 [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [How to: Control the Scope of a Variable](../Topic/How%20to:%20Control%20the%20Scope%20of%20a%20Variable%20\(Visual%20Basic\).md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)