---
title: "Checked 및 Unchecked(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked 문[C#]"
  - "예외[C#], 오버플로 검사"
  - "연산자[C#], Checked 및 Unchecked"
  - "오버플로 검사[C#]"
  - "문[C#], Checked 및 Unchecked"
  - "unchecked 문[C#]"
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Checked 및 Unchecked(C# 참조)
checked 컨텍스트 또는 unchecked 컨텍스트에서 C\# 문을 실행할 수 있습니다.  checked 컨텍스트에서는 산술 오버플로가 있으면 예외가 발생합니다.  unchecked 컨텍스트에서는 산술 오버플로가 무시되며 결과가 잘립니다.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) checked 컨텍스트를 지정합니다.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) unchecked 컨텍스트를 지정합니다.  
  
 `checked`도 `unchecked`도 지정하지 않으면 기본 컨텍스트는 컴파일러 옵션 등의 외부 요인에 따라 달라집니다.  
  
 오버플로 검사의 영향을 받는 작업은 다음과 같습니다.  
  
-   정수 계열 형식에 다음의 미리 정의된 연산자를 사용하는 식  
  
     `++`  `--` \- \(단항\)   `+` \-   `*` `/`  
  
-   정수 형식 간의 명시적 숫자 변환  
  
 [\/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) 컴파일러 옵션을 사용하면 `checked` 또는 `unchecked` 키워드의 범위에 명시적으로 포함되지 않은 모든 정수 산술 문에 대해 checked 또는 unchecked 컨텍스트를 지정할 수 있습니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [문 키워드](../../../csharp/language-reference/keywords/statement-keywords.md)