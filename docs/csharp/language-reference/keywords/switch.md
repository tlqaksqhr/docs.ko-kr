---
title: "switch(C# 참조) | Microsoft Docs"
ms.date: "2017-03-07"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "switch_CSharpKeyword"
  - "switch"
  - "case"
  - "case_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "switch 문[C#]"
  - "switch 키워드[C#]"
  - "case 문[C#]"
  - "default 키워드[C#]"
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 47
---
# switch(C# 참조)
`switch` 문은 실행할 *스위치 섹션*을 후보 목록에서 선택하는 제어문입니다.  
  
 `switch` 문에는 스위치 섹션이 하나 이상 포함됩니다.  각 스위치 섹션에는 하나 이상의 *case 레이블* 및 하나 이상의 문이 있습니다.  다음 예제에서는 세 개의 스위치 섹션이 있는 간단한 `switch` 문을 보여 줍니다.  각 스위치 섹션에는 `case 1`과 같은 하나의 case 레이블과 두 개의 문이 있습니다.  
  
 [!code-cs[csrefKeywordsSelection#7](../../../csharp/language-reference/keywords/codesnippet/csharp/switch_1.cs)]  
  
## 설명  
 각 case 레이블은 상수 값을 지정합니다.  switch 문은 case 레이블과 *switch 식*의 값\(위의 예제에서 `caseSwitch`\)이 일치하는 스위치 섹션으로 제어를 보냅니다.  일치하는 값이 들어 있는 case 레이블이 없는 경우 `default` 섹션\(있는 경우\)으로 제어를 보냅니다.  `default` 섹션이 없으면 어떠한 작업도 수행되지 않으며 `switch` 문 외부로 제어를 보냅니다.  이전 예제에서는 `case 1`이 `caseSwitch` 값과 일치하기 때문에 첫 번째 스위치 섹션의 문이 실행됩니다.  
  
 `switch` 문에 포함할 수 있는 스위치 섹션의 수에는 제한이 없으며 각 섹션에는 하나 이상의 case 레이블을 포함할 수 있습니다\(아래 예제의 문자열 case 레이블 참조\).  하지만 두 case 레이블에 동일한 상수 값을 포함할 수는 없습니다.  
  
 선택한 스위치 섹션에서 문 목록의 실행은 첫 번째 문으로 시작하고 일반적으로 `break`, `goto case`, `return` 또는 `throw` 같은 점프문에 도달할 때까지 문 목록 전체를 진행합니다.  이 경우 `switch` 문 외부 또는 다른 case 레이블로 제어를 보냅니다.  
  
 C\+\+와 달리 C\#은 한 스위치 섹션에서 다음 스위치 섹션으로 실행을 계속하는 것을 허용하지 않습니다.  다음 코드는 오류를 발생시킵니다.  
  
```c#  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
  
 C\#의 경우 요구 사항에 따라 마지막 섹션을 포함한 스위치 섹션의 끝에 도달할 수 없어야 합니다.  즉, 다른 언어와 달리 코드에서 다음 스위치 섹션으로 진행하지 않습니다.  이 요구 사항은 대개 `break` 문을 사용하여 충족할 수 있지만, 문 목록의 끝에 도달할 수 없도록 보장한다는 점에서 다음 사례도 유효합니다.  
  
```c#  
case 4:  
    while (true)  
        Console.WriteLine("Endless looping. . . .");  
```  
  
## 예제  
 다음 예제에서는 `switch` 문의 요구 사항과 기능을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsSelection#9](../../../csharp/language-reference/keywords/codesnippet/csharp/switch_2.cs)]  
  
## 예제  
 마지막 예제에서는 문자열 변수 `str` 및 문자열 case 레이블이 실행 흐름을 제어합니다.  
  
 [!code-cs[csrefKeywordsSelection#8](../../../csharp/language-reference/keywords/codesnippet/csharp/switch_3.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [switch 문 \(C\+\+\)](/visual-cpp/cpp/switch-statement-cpp)   
 [if\-else](../../../csharp/language-reference/keywords/if-else.md)