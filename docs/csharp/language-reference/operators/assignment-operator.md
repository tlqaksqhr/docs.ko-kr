---
title: "= 연산자(C# 참조) | Microsoft Docs"
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
  - "=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "= 연산자[C#]"
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# = 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`=` 연산자는 오른쪽 피연산자의 값을 왼쪽 피연산자가 나타내는 저장 위치, 속성 또는 인덱서에 저장하고 결과 값을 반환합니다.  피연산자는 같은 형식이거나 암시적으로 오른쪽 피연산자를 왼쪽 피연산자 형식으로 변환할 수 있어야 합니다.  
  
## 설명  
 대입 연산자\(\=\)는 오버로드할 수 없습니다.  그러나 형식에 대한 암시적 변환 연산자를 정의하여 이러한 형식에서 할당 연산자를 사용할 수 있습니다.  자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)를 참조하십시오.  
  
## 예제  
 [!CODE [csRefOperators#49](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#49)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)