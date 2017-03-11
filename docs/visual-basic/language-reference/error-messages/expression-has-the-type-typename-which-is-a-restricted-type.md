---
title: "Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc31393"
  - "vbc31393"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31393"
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

정규식이 공용 언어 런타임\(CLR\)에서 boxing할 수 없는 형식으로 계산되지만 boxing이 필요한 멤버에 액세스합니다.  
  
 *boxing*은 형식을 `Object` 또는 경우에 따라 <xref:System.ValueType>으로 변환하는 데 필요한 처리를 의미합니다.  공용 언어 런타임\(CLR\)에서는 <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle> 및 <xref:System.TypedReference>와 같은 특정 구조체 형식을 boxing할 수 없습니다.  
  
 이 정규식은 제한된 형식을 사용하여 <xref:System.Object.GetHashCode%2A> 또는 <xref:System.Object.ToString%2A>과 같이 <xref:System.Object> 또는 <xref:System.ValueType>에서 상속된 메서드를 호출하려고 시도합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]는 이 메서드에 액세스하기 위해 암시적 boxing 변환을 시도했으며 이 경우 이 오류가 발생합니다.  
  
 **오류 ID:** BC31393  
  
### 이 오류를 해결하려면  
  
1.  해당 형식으로 계산되는 정규식을 찾습니다.  
  
2.  문에서 <xref:System.Object> 또는 <xref:System.ValueType>에서 상속된 메서드를 호출하려고 시도하는 부분을 찾습니다.  
  
3.  메서드 호출을 수행하지 않도록 해당 문을 다시 작성합니다.  
  
## 참고 항목  
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)