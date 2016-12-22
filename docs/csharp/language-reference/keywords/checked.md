---
title: "checked(C# 참조) | Microsoft Docs"
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
  - "checked_CSharpKeyword"
  - "checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked 키워드[C#]"
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# checked(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`checked` 키워드는 정수 계열 형식의 산술 연산 및 변환에 대한 오버플로 검사를 명시적으로 활성화하는 데 사용됩니다.  
  
 기본적으로 식이 대상 형식의 범위를 벗어난 값을 생성하는 경우 상수 값만 포함된 식에서 컴파일러 오류가 발생합니다.  식이 상수가 아닌 값을 하나 이상 포함하는 경우 컴파일러에서 오버플로를 검색하지 않습니다.  다음 예제에서는 `i2`에 할당된 식을 평가해도 컴파일러 오류가 발생하지 않습니다.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 기본적으로 상수가 아닌 이러한 식에서는 런타임에 오버플로가 확인되지 않으며, 오버플로 예외가 발생하지 않습니다.  이전 예제에서는 두 양의 정수의 합계로 \-2,147,483,639를 표시합니다.  
  
 컴파일러 옵션, 환경 구성 또는 `checked` 키워드 사용을 통해 오버플로 검사를 활성화할 수 있습니다.  다음 예제에서는 `checked` 식이나 `checked` 블록을 사용하여 런타임에 이전 합계에 의해 생성된 오버플로를 검색하는 방법을 보여 줍니다.  두 예제에서 모두 오버플로 예외가 발생합니다.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md) 키워드를 사용하여 오버플로 검사를 차단할 수 있습니다.  
  
## 예제  
 이 샘플에서는 `checked`를 사용하여 런타임에 오버플로 검사를 활성화하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)