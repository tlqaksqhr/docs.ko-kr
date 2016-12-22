---
title: "No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39; | Microsoft Docs"
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
  - "bc30737"
  - "vbc30737"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30737"
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

명령줄 응용 프로그램에 `Sub Main`이 정의되어 있어야 합니다.  `Main`은 클래스에 정의된 경우 `Public Shared`로 선언되어야 하며, 모듈에 정의된 경우 `Public`으로 선언되어야 합니다.  
  
 `Main`에 대한 자세한 내용은 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/ko-kr/9d030b60-e148-4366-a462-69532f02294c)을 참조하십시오.  
  
 **오류 ID:** BC30737  
  
### 이 오류를 해결하려면  
  
-   프로젝트에 대해 `Public Sub Main` 프로시저를 정의합니다.  클래스 내에서 정의하는 경우에만 `Shared`로 선언합니다.  
  
## 참고 항목  
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/ko-kr/9d030b60-e148-4366-a462-69532f02294c)   
 [Structure of a Visual Basic Program](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)