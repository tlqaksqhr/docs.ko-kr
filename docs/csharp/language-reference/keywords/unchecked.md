---
title: "unchecked(C# 참조) | Microsoft Docs"
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
  - "unchecked_CSharpKeyword"
  - "unchecked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unchecked 키워드[C#]"
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# unchecked(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`unchecked` 키워드는 정수 계열 형식의 산술 연산 및 변환에 대한 오버플로 검사를 비활성화하는 데 사용됩니다.  
  
 unchecked 컨텍스트에서 식의 결과가 대상 형식의 범위를 벗어나는 경우 오버플로에 플래그가 지정되지 않습니다.  예를 들어, 다음 예제의 계산은 `unchecked` 블록이나 식에서 수행되므로 결과가 정수로서는 너무 크다는 사실이 무시되고 `int1`에 값 \-2,147,483,639이 할당됩니다.  
  
 [!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 `unchecked` 환경을 제거하면 컴파일 오류가 발생합니다.  식의 모든 조건은 상수이기 때문에 컴파일 타임에 오버플로를 검색할 수 있습니다.  
  
 상수가 아닌 조건을 포함하는 식은 기본적으로 컴파일 타임과 런타임에 확인되지 않습니다.  checked 환경을 사용하도록 설정하는 방법에 대한 자세한 내용은 [checked](../../../csharp/language-reference/keywords/checked.md)를 참조하십시오.  
  
 오버플로 검사에는 시간이 걸리기 때문에 오버플로 위험이 있는 경우 unchecked 코드를 사용하면 성능이 향상될 수 있습니다.  그러나 오버플로가 발생할 수 있는 경우 checked 환경을 사용해야 합니다.  
  
## 예제  
 이 샘플에서는 `unchecked` 키워드를 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [checked](../../../csharp/language-reference/keywords/checked.md)