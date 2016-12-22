---
title: "방법: 쿼리 결과를 메모리에 저장(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ 쿼리 결과 저장소[C#의 LINQ]"
  - "쿼리 식[C#의 LINQ], 결과 저장"
ms.assetid: 7271597f-3523-4f7b-b088-1eeffe913b2d
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 쿼리 결과를 메모리에 저장(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

쿼리는 기본적으로 데이터를 검색하고 구성하는 방법에 대한 명령 집합입니다.  쿼리를 실행하려면 해당 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드를 호출해야 합니다.  이 호출은 `foreach` 루프를 사용하여 요소를 반복하는 경우에 요청됩니다.  쿼리를 평가 하 고 실행 하지 않고 해당 결과 저장 하는 `foreach` 루프, 다음 방법 중 하나에서 쿼리 변수를 호출 하기만 하면:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 쿼리 결과를 저장하는 경우 다음의 예제와 같이 새 변수에 반환된 컬렉션 개체를 할당하는 것이 좋습니다.  
  
## 예제  
 [!code-cs[csProgGuideLINQ#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  
## 코드 컴파일  
  
-   .NET Framework 버전 3.5를 대상으로 하는 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] 프로젝트를 만듭니다.  기본적으로 프로젝트에는 System.Core.dll에 대한 참조 및 System.Linq 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
-   프로젝트에 코드를 복사합니다.  
  
-   F5 키를 눌러 프로그램을 컴파일하고 실행합니다.  
  
-   아무 키나 눌러 콘솔 창을 닫습니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)