---
title: "* 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "*_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "* 연산자[C#]"
  - "곱하기 연산자(*)[C#]"
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# * 연산자(C# 참조)
곱하기 연산자\(`*`\)는 피연산자의 곱을 계산합니다.  역참조 연산자를 사용하면 포인터를 읽고 쓸 수도 있습니다.  
  
## 설명  
 모든 숫자 형식에는 \* 연산자가 미리 정의되어 있습니다.  
  
 `*` 연산자는 포인터 형식의 선언과 포인터의 역참조에도 사용됩니다.  이 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드로 표시되었으며 [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션이 필요한 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.  역참조 연산자를 간접 참조 연산자라고도 합니다.  
  
 사용자 정의 형식으로 이항 `*` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#50)]  
  
## 예제  
 [!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#51)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)