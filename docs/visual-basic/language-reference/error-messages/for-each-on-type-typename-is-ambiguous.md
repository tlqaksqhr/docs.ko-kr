---
title: "&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32096"
  - "bc32096"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32096"
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`For Each` 문이 둘 이상의 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드를 포함하는 반복기 변수를 지정합니다.  
  
 반복기 변수는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 `Collections` 네임스페이스 중 하나에서 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 구현하는 형식이어야 합니다.  각 구문에 대해 다른 형식 인수를 사용하여 클래스에 둘 이상의 생성된 제네릭 인터페이스를 구현할 수 있습니다.  이런 식으로 구현하는 클래스가 반복기 변수에 사용되면 해당 변수는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드를 둘 이상 포함하게 됩니다.  이런 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 호출할 메서드를 선택할 수 없습니다.  
  
 **오류 ID:** BC32096  
  
### 이 오류를 해결하려면  
  
-   [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md)를 사용하여 반복기 변수 형식을 사용할 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드를 정의하는 인터페이스로 캐스팅합니다.  
  
## 참고 항목  
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Interfaces](../../../visual-basic/reference/command-line-compiler/index.md)