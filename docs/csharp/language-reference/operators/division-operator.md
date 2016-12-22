---
title: "/ 연산자(C# 참조) | Microsoft Docs"
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
  - "/_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/ 연산자[C#]"
  - "나누기 연산자[C#]"
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# / 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

나누기 연산자 \(`/`\)는 첫째 피연산자에서 둘째 피연산자를 나눕니다.  모든 숫자 형식에는 \/ 연산자가 미리 정의되어 있습니다.  
  
## 설명  
 사용자 정의 형식으로 `/` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  `/` 연산자를 오버로드하면 [\/\= 연산자](../../../csharp/language-reference/operators/subtraction-assignment-operator.md)도 암시적으로 오버로드됩니다.  
  
 두 정수에 대해 나누기를 수행하면 결과는 항상 정수입니다.  예를 들어, 결과는 7 \/ 3 2입니다.  7의 나머지 부분을 확인 하려면 \/ 3, 나머지 연산자 사용 \([%](../../../csharp/language-reference/operators/modulus-operator.md)\).  몫을 유리수나 분수로 가져오려면 피제수 또는 제수를 `float` 형식이나 `double` 형식으로 지정합니다.  다음 예제와 같이 숫자는 소수점 오른쪽에 넣어의 배당 또는 제 수는 소수점으로 표현 하는 경우 암시적으로 형식을 지정할 수 있습니다.  
  
## 예제  
 [!CODE [csRefOperators#42](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#42)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)