---
title: "- 연산자(C# 참조) | Microsoft Docs"
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
  - "-_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "- 연산자[C#]"
  - "빼기 연산자(-)[C#]"
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# - 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`-` 연산자는 단항 연산자로 사용하거나 이항 연산자로 사용할 수 있습니다.  
  
## 설명  
 단항 `-` 연산자는 모든 숫자 형식에 대해 미리 정의되어 있습니다.  숫자 형식에 대한 단항 `-` 연산의 결과는 피연산자의 숫자 부정입니다.  
  
 이항 `-` 연산자는 모든 숫자 형식과 열거형에 대해 첫째 피연산자에서 둘째 피연산자를 빼도록 미리 정의되어 있습니다.  
  
 또한 대리자 형식도 이항 `-` 연산자를 제공합니다. 이 경우에는 대리자 제거를 수행합니다.  
  
 사용자 정의 형식으로 단항 `-` 연산자와 이항 `-` 연산자를 오버로드할 수 있습니다.  자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  
  
## 예제  
 [!CODE [csRefOperators#40](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#40)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)