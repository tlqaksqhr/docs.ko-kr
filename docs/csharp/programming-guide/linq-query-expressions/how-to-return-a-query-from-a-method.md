---
title: "방법: 메서드에서 쿼리 반환(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "메서드 반환 쿼리[C#]"
  - "쿼리[C#의 LINQ], 메서드 반환 쿼리"
  - "쿼리 식[C#의 LINQ], 메서드 반환 쿼리"
ms.assetid: 9d6f20a7-f085-44cf-9df3-71948255ec68
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 메서드에서 쿼리 반환(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 예제에서는 메서드의 쿼리를 반환 값 및 `out` 매개 변수로 반환하는 방법을 보여 줍니다.  
  
 모든 쿼리는 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601> 형식이거나 <xref:System.Linq.IQueryable%601>과 같은 파생 형식이어야 합니다.  따라서 쿼리를 반환하는 메서드의 모든 반환 값 또는 `out` 매개 변수도 이와 같은 형식이어야 합니다.  메서드에서 쿼리를 <xref:System.Collections.Generic.List%601> 또는 <xref:System.Array> 형식으로 구체화할 경우 해당 메서드는 쿼리 자체가 아니라 쿼리 결과를 반환하는 것으로 간주됩니다.  메서드에서 반환되는 쿼리 변수는 구성 또는 수정이 가능합니다.  
  
## 예제  
 다음 예제에서 첫 번째 메서드는 쿼리를 반환 값으로 반환하고 두 번째 메서드는 쿼리를 `out` 매개 변수로 반환합니다.  두 경우 모두 반환되는 것은 쿼리 결과가 아니라 쿼리 자체입니다.  
  
 [!code-cs[csProgGuideLINQ#80](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-a-query-from-a-method_1.cs)]  
  
## 코드 컴파일  
  
-   .NET Framework 버전 3.5 이상을 대상으로 하는 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] 프로젝트를 만듭니다.  기본적으로 프로젝트에는 System.Core.dll에 대한 참조 및 System.Linq 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
-   클래스를 예제의 코드로 바꿉니다.  
  
-   F5 키를 눌러 프로그램을 컴파일하고 실행합니다.  
  
-   아무 키나 눌러 콘솔 창을 닫습니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)