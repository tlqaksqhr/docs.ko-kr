---
title: "Type &lt;typename&gt; is not CLS-compliant | Microsoft Docs"
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
  - "bc40041"
  - "vbc40041"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40041"
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type &lt;typename&gt; is not CLS-compliant
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변수, 속성 또는 함수 반환은 CLS 규격이 아닌 데이터 형식을 사용하여 선언합니다.  
  
 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격인 응용 프로그램의 경우 CLS 규격 형식만 사용해야 합니다.  
  
 다음과 같은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **오류 ID:** BC40041  
  
### 이 오류를 해결하려면  
  
-   응용 프로그램이 CLS 규격이어야 하는 경우 이 요소의 데이터 형식을 가장 가까운 CLS 규격 형식으로 변경합니다.  예를 들어, 2,147,483,647 이상의 값 범위가 필요하지 않으면 `UInteger` 대신 `Integer`를 사용할 수도 있습니다.  확장 범위가 필요하면 `UInteger`를 `Long`으로 바꿀 수 있습니다.  
  
-   응용 프로그램이 CLS 규격일 필요가 없는 경우 아무 것도 변경하지 않아도 됩니다.  하지만 CLS 규격이 아닌 것을 알고 있어야 합니다.  
  
## 참고 항목  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)