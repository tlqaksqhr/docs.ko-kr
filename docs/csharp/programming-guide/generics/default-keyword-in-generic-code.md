---
title: "제네릭 코드의 default 키워드(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "default 키워드[C#], 제네릭 프로그래밍"
  - "제네릭[C#], default 키워드"
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 제네릭 코드의 default 키워드(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

제네릭 클래스 및 메서드에서 다음과 같은 내용을 미리 알지 못하는 경우 매개 변수화된 형식 T에 기본값을 할당하는 방법에 대한 문제가 발생합니다.  
  
-   T가 참조 형식인지 값 형식인지 여부  
  
-   T가 값 형식인 경우 숫자 값인지 구조체인지 여부  
  
 t가 매개 변수화된 형식 T의 변수인 경우 "t \= null"과 같은 구문은 T가 참조 형식인 경우에만 유효하고 "t \= 0"은 구조체가 아닌 숫자 값 형식인 경우에만 사용할 수 있습니다.  참조 형식에 대해서는 null을 반환하고 숫자 값 형식에는 0을 반환하는 `default` 키워드를 사용하면 이 문제를 해결할 수 있습니다.  구조체에 대해서는 멤버가 값 형식인지 참조 형식인지 여부에 따라 0 또는 null로 초기화된 구조체의 각 멤버가 반환됩니다.  null 허용 값 형식의 경우 default는 다른 구조체와 같이 초기화되는 <xref:System.Nullable%601?displayProperty=fullName>을 반환합니다.  
  
 `GenericList<T>` 클래스에 있는 다음 예제에서는 `default` 키워드를 사용하는 방법을 보여 줍니다.  자세한 내용은 [제네릭 개요](../../../csharp/programming-guide/generics/introduction-to-generics.md)를 참조하십시오.  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭](../../../visual-basic/reference/command-line-compiler/index.md)   
 [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)   
 [제네릭](../Topic/Generics%20in%20the%20.NET%20Framework.md)