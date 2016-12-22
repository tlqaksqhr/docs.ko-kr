---
title: "Out of stack space (Visual Basic) | Microsoft Docs"
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
  - "vbrID28"
dev_langs: 
  - "VB"
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Out of stack space (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

스택은 실행 프로그램의 요청에 따라 동적으로 확대하고 축소하는 메모리의 작업 공간인데  해당 제한이 초과했습니다.  
  
### 이 오류를 해결하려면  
  
1.  프로시저가 너무 많이 중첩되지 않았는지 확인합니다.  
  
2.  재귀 프로시저가 올바로 끝났는지 확인합니다.  
  
3.  지역 변수 공간이 모자라면 일부 변수를 모듈 수준으로 선언해 봅니다.  `Property`, `Sub` 또는 `Function` 키워드를 `Static`으로 선언한 다음 프로시저 안의 모든 변수를 static으로 선언할 수도 있습니다.  또는 `Static` 문을 사용하여 프로시저 안에서 개별적으로 Static 변수를 선언할 수도 있습니다.  
  
4.  고정 길이 문자열은 가변 길이 문자열보다 스택 공간을 많이 사용하므로 일부 고정 길이 문자열을 가변 길이 문자열로 다시 정의합니다.  스택 공간이 필요하지 않은 모듈 수준으로 문자열을 정의할 수도 있습니다.  
  
5.  `Calls` 대화 상자에서 스택에 활성화되어 있는 프로시저를 확인하여 중첩된 `DoEvents` 함수의 개수를 확인합니다.  
  
6.  이미 스택에 있는 이벤트 프로시저를 호출하는 이벤트를 트리거하여 "이벤트 캐스케이딩"이 발생하지 않도록 합니다.  이벤트 캐스케이딩은 끝나지 않은 재귀 프로시저 호출과 비슷하지만 코드에서 명시적으로 호출되지 않고 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 호출하므로 비교적 명확하지 않습니다.  `Calls`대화 상자를 사용하여 스택에 활성화되어 있는 프로시저를 확인합니다.  
  
## 참고 항목  
 [메모리 창](/visual-studio/debugger/memory-windows)