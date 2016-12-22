---
title: "How to: Create a Collection Used by a Collection Initializer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "collection initializers [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Collection Used by a Collection Initializer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

컬렉션 이니셜라이저를 사용하여 컬렉션을 만들 경우 Visual Basic 컴파일러는 `Add` 메서드의 매개 변수가 컬렉션 이니셜라이저의 값 형식과 일치하는 컬렉션 형식의 `Add` 메서드를 검색합니다.  이 `Add` 메서드는 컬렉션을 컬렉션 이니셜라이저의 값으로 채우는 데 사용됩니다.  
  
## 예제  
 다음 예제에서는 컬렉션 이니셜라이저에서 `Order` 형식의 개체를 추가하는 데 사용할 수 있는 public `Add` 메서드가 포함된 `OrderCollection` 컬렉션을 보여 줍니다.  `Add` 메서드를 통해 약식 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#4)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#1)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#2](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#2)]  
  
 [!CODE [VbVbalrCollectionInitializersHowTo2#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2#3)]  
  
## 참고 항목  
 [Collection Initializers](../../../../visual-basic/reference/command-line-compiler/index.md)   
 [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)