---
title: "Underlying type &lt;typename&gt; of Enum is not CLS-compliant | Microsoft Docs"
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
  - "vbc40032"
  - "bc40032"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40032"
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Underlying type &lt;typename&gt; of Enum is not CLS-compliant
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 열거형에 지정된 데이터 형식이 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격의 일부가 아닙니다.  [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 및 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 이 데이터 형식을 지원하므로 구성 요소 내에 오류가 있는 것은 아닙니다.  그러나 CLS 규격 코드로 작성된 다른 구성 요소가 이 데이터 형식을 지원하지 않을 수 있습니다.  이러한 구성 요소는 사용자의 구성 요소와 성공적으로 상호 작용하지 못할 수도 있습니다.  
  
 다음과 같은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40032  
  
### 이 오류를 해결하려면  
  
-   사용자의 구성 요소가 다른 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 구성 요소하고만 상호 작용하거나 다른 구성 요소와 상호 작용하지 않는 경우에는 아무 것도 변경하지 않아도 됩니다.  
  
-   [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]에 대해 작성되지 않은 구성 요소와 상호 작용하는 경우에는 구성 요소에서 이 데이터 형식을 지원할지 여부를 리플렉션을 통해 또는 문서에서 결정할 수 있습니다.  구성 요소에서 이 데이터 형식을 지원하는 경우 아무 것도 변경하지 않아도 됩니다.  
  
-   이 데이터 형식을 지원하지 않는 구성 요소와 상호 작용하는 경우에는 데이터 형식을 가장 유사한 CLS 규격 형식으로 바꿔야 합니다.  예를 들어, 2,147,483,647 이상의 값 범위가 필요하지 않으면 `UInteger` 대신 `Integer`를 사용할 수도 있습니다.  확장 범위가 필요하면 `UInteger`를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 개체 또는 COM 개체를 사용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 경우와 다르다는 것을 염두에 두고 있어야 합니다.  예를 들어, `uint`는 다른 환경에서 16비트인 경우가 많습니다.  이러한 구성 요소에 16비트 인수를 전달하는 경우 관리되는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드에서는 이 인수를 `UInteger` 대신 `UShort`로 선언하십시오.  
  
## 참고 항목  
 [리플렉션](../Topic/Reflection%20\(C%23%20and%20Visual%20Basic\).md)   
 [리플렉션](../Topic/Reflection%20in%20the%20.NET%20Framework.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)