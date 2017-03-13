---
title: "++ 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "++_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "++ 연산자[C#]"
  - "증가 연산자(++)[C#]"
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# ++ 연산자(C# 참조)
증가 연산자\(`++`\)는 피연산자를 1씩 증가합니다. 증가 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다\(`++variable` 및 `variable++`\).  
  
## 설명  
 첫 번째 형태는 전위 증가 연산입니다. 연산 결과는 증가된 후의 피연산자 값입니다.  
  
 두 번째 형태는 후위 증가 연산입니다. 연산 결과는 증가되기 전의 피연산자 값입니다.  
  
 숫자 및 열거형 형식에는 미리 정의된 증가 연산자가 있습니다. 사용자 정의 형식은 `++` 연산자를 오버로드할 수 있습니다. 정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)