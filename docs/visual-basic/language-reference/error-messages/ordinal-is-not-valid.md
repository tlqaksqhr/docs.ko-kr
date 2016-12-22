---
title: "Ordinal is not valid | Microsoft Docs"
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
  - "vbrID452"
dev_langs: 
  - "VB"
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ordinal is not valid
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

현재 DLL\(동적 연결 라이브러리\)은 `#num` 구문을 통해 프로시저 이름 대신 숫자를 사용하여 호출됩니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   `#num` 식을 서수로 변환하는 데 실패했습니다.  
  
-   지정된 `#num`에서 DLL에 함수를 지정하지 않았습니다.  
  
-   형식 라이브러리에 잘못된 선언이 사용되어 잘못된 서수가 내부적으로 사용되었습니다.  
  
### 이 오류를 해결하려면  
  
1.  식에서 올바른 숫자를 표시했는지 확인하거나 프로시저를 이름으로 호출합니다.  
  
2.  `#num`에서 올바른 DLL의 함수를 식별하는지 확인합니다.  
  
3.  프로시저 호출을 격리시키면 주석 처리가 코드에서 제거되어 문제가 발생합니다.  프로시저에 `Declare` 문을 작성하고 문제를 형식 라이브러리 공급업체에 보고합니다.  
  
## 참고 항목  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)