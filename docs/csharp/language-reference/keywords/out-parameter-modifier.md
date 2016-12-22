---
title: "out 매개 변수 한정자(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out 매개 변수[C#]"
  - "매개 변수[C#], out"
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# out 매개 변수 한정자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`out` 키워드는 인수를 참조로 전달하는 데 사용됩니다.  이는 [ref](../../../csharp/language-reference/keywords/ref.md) 키워드와 비슷하지만 `ref`의 경우 변수를 전달하기 전에 초기화해야 한다는 점에서 차이가 있습니다.  `out` 매개 변수를 사용하려면 메서드 정의와 호출하는 메서드에서 모두 `out` 키워드를 명시적으로 사용해야 합니다.  예를 들면 다음과 같습니다.  
  
 [!CODE [csrefKeywordsMethodParams#1](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#1)]  
  
 `out` 인수로 전달되는 변수는 이를 전달하기 전에 초기화할 필요가 없지만 호출되는 메서드는 메서드 반환 이전에 값을 할당해야 합니다.  
  
 `ref` 및 `out` 키워드는 다른 런타임 동작을 가져오지만 컴파일 타임에 메서드 시그니처의 일부로 간주되지 않습니다.  따라서 한 메서드는 `ref` 인수를 사용하고 다른 메서드는 `out` 인수를 사용하는 것이 유일한 차이점인 경우 메서드를 오버로드할 수 없습니다.  예를 들어, 다음 코드는 컴파일되지 않습니다.  
  
 [!CODE [csrefKeywordsMethodParams#2](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#2)]  
  
 그러나 한 메서드가 `ref` 또는 `out` 인수를 사용하고 다른 메서드는 두 인수 중 어느 것도 사용하지 않는 경우 다음과 같이 오버로드할 수 있습니다.  
  
 [!CODE [csrefKeywordsMethodParams#3](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#3)]  
  
 속성은 변수가 아니므로 `out` 매개 변수로 전달할 수 없습니다.  
  
 배열 전달에 대한 자세한 내용은 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하십시오.  
  
 사용할 수 없습니다는 `ref` 및 `out` 다음과 같은 종류의 방법에 대 한 키워드:  
  
-   비동기 메서드를 사용 하 여 정의 된  [비동기](../../../visual-basic/language-reference/modifiers/async.md) 한정자입니다.  
  
-   포함 하는 반복기 메서드는  [수익률을 반환 합니다.](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문.  
  
## 예제  
 메서드에서 값을 여러 개 반환해야 하는 경우 `out` 메서드를 선언하는 것이 좋습니다.  다음 예제에서는 `out`을 사용하여 한 번의 메서드 호출로 변수 세 개를 반환합니다.  세 번째 인수에는 null이 할당됩니다.  이렇게 하면 메서드에서 값을 선택적으로 반환할 수 있습니다.  
  
 [!CODE [csrefKeywordsMethodParams#4](../CodeSnippet/VS_Snippets_VBCSharp/csrefKeywordsMethodParams#4)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md)