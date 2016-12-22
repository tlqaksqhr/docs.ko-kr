---
title: "Erase Statement (Visual Basic) | Microsoft Docs"
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
  - "vb.Erase"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Erase keyword"
  - "Erase statement"
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Erase Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

배열 변수를 해제하고 배열 변수의 요소에 사용된 메모리의 할당을 취소하는 데 사용합니다.  
  
## 구문  
  
```  
Erase arraylist  
```  
  
## 요소  
 `arraylist`  
 필수 요소.  지울 배열 변수의 목록으로  변수가 여러 개 있으면 쉼표로 구분됩니다.  
  
## 설명  
 `Erase` 문은 프로시저 수준에서만 사용될 수 있습니다.  즉, 프로시저 내에서는 배열을 릴리스할 수 있지만 클래스나 모듈 수준에서는 배열을 릴리스할 수 없습니다.  
  
 `Erase` 문을 사용하는 것은 각 배열 변수에 `Nothing`을 할당하는 것과 같습니다.  
  
## 예제  
 다음 예제에서는 `Erase` 문을 사용하여 두 배열을 지우고 해당 메모리를 비웁니다. 각각 1000개 및 100개의 저장소 요소입니다.  그런 다음 `ReDim` 문이 새 배열 인스턴스를 3차원 배열에 할당합니다.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## 참고 항목  
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)