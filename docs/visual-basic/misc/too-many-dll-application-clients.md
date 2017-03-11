---
title: "DLL 응용 프로그램 클라이언트가 너무 많습니다. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID47"
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# DLL 응용 프로그램 클라이언트가 너무 많습니다.
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에 대한 DLL\(동적 연결 라이브러리\)은 제한된 수의 호스트 응용 프로그램 액세스만 허용할 수 있습니다. 사용자 응용 프로그램 및 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 호스트인 다른 응용 프로그램\(일부는 사용자 응용 프로그램에서 액세스할 수 있음\)이 동시에 모두 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] DDL에 액세스하려고 합니다.  
  
### 이 오류를 해결하려면  
  
-   [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에 액세스하는 열려 있는 응용 프로그램 수를 줄입니다.  
  
## 참고 항목  
 [Error Types](../../visual-basic/programming-guide/language-features/error-types.md)