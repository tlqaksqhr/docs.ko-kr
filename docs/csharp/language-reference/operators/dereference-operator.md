---
title: "-&gt; 연산자(C# 참조) | Microsoft Docs"
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
  - "->_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-> 연산자[C#]"
  - "멤버 액세스 연산자(->)[C#]"
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# -&gt; 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

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
 [!CODE [csRefOperators#15](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#15)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)