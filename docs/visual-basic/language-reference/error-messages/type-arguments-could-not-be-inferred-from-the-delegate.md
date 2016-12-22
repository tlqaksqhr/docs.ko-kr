---
title: "Type arguments could not be inferred from the delegate | Microsoft Docs"
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
  - "bc36564"
  - "vbc36564"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36564"
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type arguments could not be inferred from the delegate
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

할당문이 `AddressOf`를 사용하여 제네릭 프로시저의 주소를 대리자에게 할당하지만 형식 인수를 제니릭 프로시저에 제공하지 않습니다.  
  
 일반적으로 제네릭 형식을 호출할 때 제네릭 형식이 정의하는 각 형식 매개 변수에 대해 형식 인수를 제공합니다.  형식 인수를 제공하지 않는 경우 컴파일러는 형식 매개 변수에 전달될 형식을 유추하려고 합니다.  컴파일러가 형식을 유추할 수 있도록 충분한 정보가 컨텍스트에 제공되지 않는 경우 오류가 발생합니다.  
  
 **오류 ID:** BC36564  
  
### 이 오류를 해결하려면  
  
-   `AddressOf` 식의 제네릭 프로시저에 대한 형식 인수를 지정합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)