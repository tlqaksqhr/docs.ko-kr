---
title: "-&gt; 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "->_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-> 연산자[C#]"
  - "멤버 액세스 연산자(->)[C#]"
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# -&gt; 연산자(C# 참조)
`->` 연산자는 포인터 역참조와 멤버 액세스를 결합합니다.  
  
## 설명  
 다음 형식의 식은  
  
```  
x->y  
```  
  
 다음 식과 같습니다. 여기서 `x`는 `T*` 형식의 포인터이며 `y`는 `T`의 멤버입니다.  
  
```  
(*x).y  
```  
  
 `->` 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)로 표시된 코드에서만 사용할 수 있습니다.  
  
 `->` 연산자는 오버로드되지 않습니다.  
  
## 예제  
 [!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#15)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)