---
title: "속성 및 인덱서 비교(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "인덱서[C#], 속성과 비교"
  - "속성[C#], 인덱서와 비교"
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# 속성 및 인덱서 비교(C# 프로그래밍 가이드)
인덱서는 속성과 비슷합니다.  다음 표에 나와 있는 차이점을 제외하면 접근자에 정의된 모든 규칙이 인덱서 접근자에도 적용됩니다.  
  
|Property|인덱서|  
|--------------|---------|  
|공용 데이터 멤버인 것처럼 메서드를 호출할 수 있습니다.|개체 자체의 배열 표기법을 사용하여 개체의 내부 컬렉션 요소에 액세스할 수 있습니다.|  
|단순한 이름을 통해 액세스할 수 있습니다.|인덱스를 통해 액세스할 수 있습니다.|  
|정적 또는 인스턴스 멤버가 될 수 있습니다.|인스턴스 멤버여야 합니다.|  
|속성의 [get](../../../csharp/language-reference/keywords/get.md) 접근자에는 매개 변수가 없습니다.|인덱서의 `get` 접근자는 인덱서와 동일한 정식 매개 변수 목록을 가집니다.|  
|속성의 [set](../../../csharp/language-reference/keywords/set.md) 접근자에는 명시적인 `value` 매개 변수가 포함됩니다.|인덱서의 `set` 접근자는 [value](../../../csharp/language-reference/keywords/value.md) 매개 변수 외에도 인덱서와 동일한 정식 매개 변수 목록을 가집니다.|  
|[자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)이 있는 약식 구문을 지원합니다.|약식 구문을 지원하지 않습니다.|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)