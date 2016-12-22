---
title: "out(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "out_CSharpKeyword"
  - "out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out[C#]"
  - "out 키워드[C#]"
ms.assetid: 7e911a0c-3f98-4536-87be-d539b7536ca8
caps.latest.revision: 30
caps.handback.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# out(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`out` 컨텍스트 키워드는 두 가지 컨텍스트, 즉 [매개 변수 한정자](../../../csharp/language-reference/keywords/out-parameter-modifier.md)로 사용하거나 인터페이스와 대리자의 [제네릭 형식 매개 변수 선언](../../../csharp/language-reference/keywords/out-generic-modifier.md)에서 사용할 수 있습니다. 각 항목은 상세한 정보를 확인할 수 있는 링크입니다.  이 항목에서는 매개 변수 한정자에 대해 설명하며, [이 항목](../../../csharp/language-reference/keywords/out-generic-modifier.md)에서 제네릭 형식 매개 변수 선언에 대한 정보를 확인할 수 있습니다.  
  
 `out` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.  이러한 방식은 [ref](../../../csharp/language-reference/keywords/ref.md) 키워드와 비슷합니다. 단, `ref`의 경우에는 변수를 전달하기 전에 초기화해야 합니다.  `out` 매개 변수를 사용하려면 메서드 정의와 호출 메서드가 모두 명시적으로 `out` 키워드를 사용해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!CODE [csrefKeywordsMethodParams#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#1)]  
  
 `out` 인수로 전달되는 변수는 전달하기 전에 초기화할 필요가 없지만 호출되는 메서드는 반환되기 전에 값을 할당해야 합니다.  
  
 `ref` 및 `out` 키워드는 서로 다른 런타임 동작을 수행하지만 컴파일 타임에 메서드 시그니처의 일부로 간주되지는 않습니다.  따라서 메서드 하나는 `ref` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.  예를 들어 다음 코드는 컴파일되지 않습니다.  
  
 [!CODE [csrefKeywordsMethodParams#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#2)]  
  
 그러나 다음과 같이 메서드 하나는 `ref` 또는 `out` 인수를 사용하고 다른 하나는 인수를 사용하지 않는 경우에는 오버로드를 수행할 수 있습니다.  
  
 [!CODE [csrefKeywordsMethodParams#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#3)]  
  
 속성은 변수가 아니므로 `out` 매개 변수로 전달할 수 없습니다.  
  
 배열 전달에 대한 자세한 내용은 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.  
  
 다음과 같은 종류의 메서드에는 `ref` 및 `out` 키워드를 사용할 수 없습니다.  
  
-   [async](../../../visual-basic/language-reference/modifiers/async.md) 한정자를 사용하여 정의하는 비동기 메서드  
  
-   [yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드  
  
## 예제  
 메서드가 여러 값을 반환하도록 하려는 경우에는 `out` 메서드를 선언하면 유용합니다.  다음 예제에서는 `out`을 사용하여 단일 메서드 호출로 3개 변수를 반환합니다.  세 번째 인수는 null에 할당됩니다.  따라서 메서드가 값을 선택적으로 반환할 수 있습니다.  
  
 [!CODE [csrefKeywordsMethodParams#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#4)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)