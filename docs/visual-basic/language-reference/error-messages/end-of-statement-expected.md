---
title: "문의 끝이 필요합니다. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30205"
  - "vbc30205"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30205"
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# 문의 끝이 필요합니다.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문의 구문은 완벽하지만 문을 마치는 요소의 뒤에 추가 프로그래밍 요소가 있습니다.  모든 문의 끝에는 줄 종결자가 필요합니다.  
  
 줄 종결자는 Visual Basic 소스 파일의 문자를 줄으로 나눕니다.  줄 종결자의 예로 유니코드 캐리지 리턴 문자 \(& HD\), 유니코드 줄 바꿈 문자 \(& HA\), 유니코드 캐리지 유니코드 줄 바꿈 문자 앞에 오는 문자를 반환 합니다.  줄 종결자에 대 한 자세한 내용은 참조 하십시오 있는 [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).  
  
 **오류 ID:** BC30205  
  
### 이 오류를 해결하려면  
  
1.  다른 두 문을 같은 줄에 잘못 사용했는지 확인합니다.  
  
2.  문을 마치는 요소의 뒤에 줄 종결자를 삽입합니다.  
  
## 참고 항목  
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)