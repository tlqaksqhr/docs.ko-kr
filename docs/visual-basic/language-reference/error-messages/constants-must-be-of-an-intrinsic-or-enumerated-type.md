---
title: "Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30424"
  - "bc30424"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30424"
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

상수를 클래스, 구조체 또는 배열 형식으로 선언하거나 포함하는 제네릭 형식으로 정의된 형식 매개 변수로 선언하려고 했습니다.  
  
 상수는 내장 형식\(`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong` 또는 `UShort`\)이거나 정수 계열 형식 중 하나를 기반으로 하는 `Enum` 형식이어야 합니다.  
  
 **오류 ID:** BC30424  
  
### 이 오류를 해결하려면  
  
1.  내장 형식 또는 `Enum` 형식으로 상수를 선언합니다.  
  
2.  상수는 `True`, `False` 또는 `Nothing`과 같은 특수 값이 될 수도 있습니다.  컴파일러에서는 미리 정의된 이러한 값을 적절한 내장 형식으로 간주합니다.  
  
## 참고 항목  
 [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [데이터 형식](../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)