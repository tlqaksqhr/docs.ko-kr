---
title: "방법: 변수의 주소 가져오기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "포인터 식[C#], 주소 연산자"
  - "포인터[C#], & 연산자"
  - "변수[C#], 주소"
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 변수의 주소 가져오기(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

fixed 변수로 계산되는 단항 식의 주소를 얻으려면 주소 연산자를 사용합니다.  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 주소 연산자는 변수에만 적용할 수 있습니다.  변수가 이동 가능한 변수인 경우 해당 주소를 얻기 전에 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)을 사용하여 변수를 임시로 고정할 수 있습니다.  
  
 사용자는 직접 변수의 초기화 여부를 확인해야 합니다.  변수가 초기화되지 않았더라도 컴파일러에서는 오류 메시지를 표시하지 않습니다.  
  
 상수나 값의 주소는 가져올 수 없습니다.  
  
## 예제  
 이 예제에서는 `int`에 대한 포인터인 `p`가 선언되고 `number`라는 정수 변수의 주소가 대입됩니다.  \*p에 값을 대입하면 `number` 변수가 초기화됩니다.  이 대입문을 주석 처리하면 `number` 변수의 초기화가 제거되지만 컴파일 타임 오류는 발생하지 않습니다.  [멤버 액세스](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) 연산자 `->`를 사용하면 포인터에 저장된 주소를 가져와서 표시할 수 있습니다.  
  
 [!CODE [csProgGuidePointers#7](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#7)]  
  
 [!CODE [csProgGuidePointers#8](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#8)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)