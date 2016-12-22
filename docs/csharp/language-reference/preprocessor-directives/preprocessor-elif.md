---
title: "#elif(C# 참조) | Microsoft Docs"
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
  - "#elif"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#elif 지시문[C#]"
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #elif(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#elif`를 사용하여 복합 조건부 지시문을 만들 수 있습니다.   `#elif` 식이 계산되는 경우는 앞의 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 와 `#elif` \(선택적 요소\) 지시문 식이 모두 `true` 로 계산되지 않는 경우입니다.  `#elif` 식이 `true`가 되면 컴파일러에서는 `#elif`와 다음 조건부 지시문 사이의 모든 코드를 계산합니다.  예를 들면 다음과 같습니다.  
  
```  
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 `==`\(같음\), `!=`\(같지 않음\), `&&`\(AND\) 및 `||`\(OR\) 연산자를 사용하여 여러 기호를 계산할 수 있습니다.  괄호를 사용하여 기호와 연산자를 그룹화할 수도 있습니다.  
  
## 설명  
 `#elif`는 다음 지시문을 사용하는 경우와 같습니다.  
  
```  
#else  
#if  
```  
  
 각 `#if`에는 [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)가 필요한 반면 `#elif`는 짝이 되는 `#endif` 없이도 사용할 수 있기 때문에 `#elif`를 사용하는 것이 더 간단합니다.  
  
 `#elif` 사용 방법 예제는 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../visual-basic/reference/command-line-compiler/index.md)