---
title: "How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "collection initializers [Visual Basic]"
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컬렉션 이니셜라이저를 사용하여 컬렉션을 만들 경우 Visual Basic 컴파일러는 `Add` 메서드의 매개 변수가 컬렉션 이니셜라이저의 값 형식과 일치하는 컬렉션 형식의 `Add` 메서드를 검색합니다.  이 `Add` 메서드는 컬렉션을 컬렉션 이니셜라이저의 값으로 채우는 데 사용됩니다.  
  
 일치하는 `Add` 메서드가 없고 컬렉션에 대한 코드를 수정할 수 없는 경우에는 컬렉션 이니셜라이저에 필요한 매개 변수를 받아들이는 확장 메서드 `Add`를 추가할 수 있습니다.  이 작업은 대개 제네릭 컬렉션에 컬렉션 이니셜라이저를 사용할 때 필요합니다.  
  
## 예제  
 다음 예제에서는 컬렉션 이니셜라이저를 사용하여 `Employee` 형식의 개체를 추가할 수 있도록 확장 메서드를 제네릭 <xref:System.Collections.Generic.List%601> 형식에 추가하는 방법을 보여 줍니다.  확장 메서드를 통해 약식 컬렉션 이니셜라이저 구문을 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-an-add-ext_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-an-add-ext_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-an-add-ext_3.vb)]  
  
## 참고 항목  
 [Collection Initializers](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [How to: Create a Collection Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)