---
title: "Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant | Microsoft Docs"
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
  - "bc40027"
  - "vbc40027"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40027"
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Function` 프로시저가 `<CLSCompliant(True)>`로 표시되지만 `<CLSCompliant(False)>`로 표시되거나 아예 표시되지 않거나 CLS 규격이 아닌 형식이므로 한정되지 않은 형식을 반환합니다.  
  
 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격인 프로시저의 경우 CLS 규격 형식만 사용해야 합니다.  이는 매개 변수 형식, 반환 형식 및 모든 지역 변수 형식에 적용됩니다.  
  
 다음과 같은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 이 특성의 `isCompliant` 매개 변수를 `True`나 `False`로 설정하여 규격 준수 여부를 나타내야 합니다.  이 매개 변수의 기본값이 없으므로 값을 제공해야 합니다.  
  
 <xref:System.CLSCompliantAttribute>를 요소에 적용하지 않으면 이 요소는 CLS 규격이 아닌 것으로 간주됩니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC40027  
  
### 이 오류를 해결하려면  
  
-   `Function` 프로시저가 이 특정 형식을 반환해야 하는 경우 <xref:System.CLSCompliantAttribute>를 제거합니다.  프로시저는 CLS 규격이 될 수 없습니다.  
  
-   `Function` 프로시저가 CLS 규격이어야 하는 경우 반환 형식을 가장 가까운 CLS 규격 형식으로 변경합니다.  예를 들어, 2,147,483,647 이상의 값 범위가 필요하지 않으면 `UInteger` 대신 `Integer`를 사용할 수도 있습니다.  확장 범위가 필요하면 `UInteger`를 `Long`으로 바꿀 수 있습니다.  
  
-   자동화 개체 또는 COM 개체를 사용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 경우와 다르다는 것을 염두에 두고 있어야 합니다.  예를 들어, `int`는 다른 환경에서 16비트인 경우가 많습니다.  이러한 구성 요소에 16비트 정수를 전달하는 경우 관리되는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 이 정수를 `Integer` 대신 `Short`로 선언합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)