---
title: "Argument not optional (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID449"
dev_langs: 
  - "VB"
ms.assetid: 76e7bcf3-24ed-4cd5-945b-b98f1c76944b
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Argument not optional (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

인수의 개수와 형식은 지정된 것과 일치해야 합니다.  인수의 개수가 잘못되었거나 필수 인수를 생략했습니다.  사용자 정의 프로시저에 대한 호출에서 인수를 생략하는 것은 프로시저 정의에서 인수를 `Optional`로 선언한 경우에만 가능합니다.  
  
### 이 오류를 해결하려면  
  
1.  필요한 인수를 모두 지정합니다.  
  
2.  생략한 인수가 선택적인지 확인합니다.  선택적이 아니면 호출할 때 인수를 지정하거나 정의에서 매개 변수를 `Optional`로 선언합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)