---
title: "First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39; | Microsoft Docs"
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
  - "vbc30920"
  - "bc30920"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30920"
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

클래스 생성자가 기본 클래스 생성자를 명시적으로 호출하지 않고 암시적 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 이를 오류로 처리하는 지시문으로 표시됩니다.  
  
 파생 클래스 생성자가 기본 클래스 생성자를 호출하지 않으면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 매개 변수 없는 기본 클래스 생성자를 암시적으로 호출하려고 합니다.  인수 없이 호출할 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없으면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 암시적으로 호출할 수 없습니다.  이런 경우 필요한 생성자가 <xref:System.ObsoleteAttribute> 특성으로 표시되어 있으면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 생성자를 호출할 수 없습니다.  
  
 사용하지 않는 프로그래밍 요소의 경우 <xref:System.ObsoleteAttribute>를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.  이렇게 하는 경우 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.  `True`로 설정하면 요소를 사용하려는 시도를 컴파일러가 오류로 처리합니다.  `False`로 설정하거나 기본값인 `False`로 두면 요소를 사용하려는 시도가 있을 경우 컴파일러가 경고를 발생시킵니다.  
  
 **오류 ID:** BC30920  
  
### 이 오류를 해결하려면  
  
1.  인용된 오류 메시지를 검사하여 적절한 조치를 취합니다.  
  
2.  `MyBase.New()` 또는 `MyClass.New()` 호출을 파생 클래스에 있는 `Sub New`의 첫 번째 문으로 포함합니다.  
  
## 참고 항목  
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)