---
title: "-- 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "--_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-- 연산자[C#]"
  - "감소 연산자(--)[C#]"
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# -- 연산자(C# 참조)
감소 연산자\(`--`\)는 피연산자를 1씩 감소시킵니다.  `--variable` 및 `variable--`과 같이 감소 연산자는 피연산자의 앞이나 뒤에 올 수 있습니다.  첫째 형태는 전위 감소 연산입니다.  이 연산의 결과는 감소된 "후"의 피연산자 값입니다.  둘째 형태는 후위 감소 연산입니다.  이 연산의 결과는 감소되기 "전"의 피연산자 값입니다.  
  
## 설명  
 숫자 형식과 열거형에는 감소 연산자가 미리 정의되어 있습니다.  
  
 사용자 정의 형식으로 `--` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#8)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)