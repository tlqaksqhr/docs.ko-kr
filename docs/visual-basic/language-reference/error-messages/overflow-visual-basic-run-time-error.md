---
title: "Overflow (Visual Basic Run-Time Error) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrERRID_Overflow"
dev_langs: 
  - "VB"
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Overflow (Visual Basic Run-Time Error)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

할당 대상의 제한을 초과하여 할당하려고 할 때 오버플로가 발생했습니다.  
  
### 이 오류를 해결하려면  
  
1.  할당, 계산 및 데이터 형식 변환의 결과가 해당 값 형식에 사용할 수 있는 변수의 범위로 표현되는지 확인한 다음 필요한 경우 더 큰 범위의 값을 보유할 수 있는 형식의 변수에 값을 할당합니다.  
  
2.  속성에 대한 할당이 해당 속성 범위에 맞는지 확인합니다.  
  
3.  정수 계열로 강제 변환되도록 계산에 사용된 숫자가 정수 계열보다 크지 않은지 확인합니다.  
  
## 참고 항목  
 <xref:System.Int32.MaxValue?displayProperty=fullName>   
 <xref:System.Double.MaxValue?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)