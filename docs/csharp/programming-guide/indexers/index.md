---
title: "인덱서(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "cs.indexers"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 인덱서"
  - "인덱서[C#]"
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 인덱서(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

인덱서에서는 클래스나 구조체의 인스턴스를 배열처럼 인덱싱할 수 있습니다.  인덱서는 해당 접근자가 매개 변수를 사용한다는 점을 제외하면 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)과 유사합니다.  
  
 다음 예제에서는 제네릭 클래스를 정의하고 값을 할당하고 검색하는 방법으로 간단한 [get](../../../csharp/language-reference/keywords/get.md) 및 [set](../../../csharp/language-reference/keywords/set.md) 접근자 메서드를 제공합니다.  `Program` 클래스는 이 클래스의 인스턴스를 만들어 문자열을 저장합니다.  
  
 [!code-cs[csProgGuideIndexers#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/index_1.cs)]  
  
> [!NOTE]
>  추가 예제는 [관련 단원](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections)을 참조하세요.  
  
## 식 본문 정의  
 일반적으로 식의 결과와 함께 바로 반환되는 인덱서를 사용합니다.  `=>`를 사용하여 이러한 인덱서를 정의하는 구문 바로 가기는 다음과 같습니다.  
  
```c#  
public Customer this[long id] => store.LookupCustomer(id);  
  
```  
  
 인덱서는 읽기 전용이어야 하며, `get` 접근자 키워드를 사용하지 않습니다.  
  
## 인덱서 개요  
  
-   인덱서를 사용하면 배열과 유사한 방식으로 개체를 인덱싱할 수 있습니다.  
  
-   `get` 접근자는 값을 반환합니다.  `set` 접근자는 값을 할당합니다.  
  
-   [this](../../../csharp/language-reference/keywords/this.md) 키워드는 인덱서를 정의하는 데 사용됩니다.  
  
-   [value](../../../csharp/language-reference/keywords/value.md) 키워드는 `set` 인덱서에서 할당하는 값을 정의하는 데 사용됩니다.  
  
-   인덱서는 정수 값으로 인덱싱될 필요가 없으며, 특정 조회 메커니즘을 정의하는 방법을 결정해야 합니다.  
  
-   인덱서는 오버로드될 수 있습니다.  
  
-   예를 들어 인덱서는 2차원 배열에 액세스하는 경우 둘 이상의 정식 매개 변수를 사용할 수 있습니다.  
  
##  <a name="BKMK_RelatedSections"></a> 관련 단원  
  
-   [인덱서 사용](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [인터페이스의 인덱서](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [속성 및 인덱서 비교](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [접근자 액세스 가능성 제한](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)