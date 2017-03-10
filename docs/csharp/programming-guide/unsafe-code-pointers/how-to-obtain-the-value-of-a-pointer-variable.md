---
title: "방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "포인터 식[C#], 간접 참조"
  - "포인터[C#], * 연산자"
  - "포인터[C#], 간접 참조"
  - "변수[C#], 포인터"
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)
포인터가 가리키는 위치의 변수를 가져오려면 포인터 간접 참조 연산자를 사용합니다.  식의 형태는 다음과 같습니다. 여기에서  `p`는 포인터 형식입니다.  
  
```  
*p;  
```  
  
 포인터 형식이 아닌 다른 형식의 식에는 단항 간접 참조 연산자를 사용할 수 없습니다.  또한 이를 [void](../../../csharp/language-reference/keywords/void.md) 포인터에 적용할 수 없습니다.  
  
 간접 참조 연산자를 [null](../../../csharp/language-reference/keywords/null.md) 포인터에 적용하면 구현에 따라 결과가 달라집니다.  
  
## 예제  
 다음 예제에서는 서로 다른 형식의 포인터를 사용하여 `char` 형식의 변수에 액세스합니다.  `theChar`의 주소는 실행할 때마다 달라집니다. 변수에 할당되는 실제 주소가 변경될 수 있기 때문입니다.  
  
 [!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#5)]  
  
 [!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#6)]  
  
  **Value of theChar \= Z**   
**Address of theChar \= 12F718**  
**Value of pChar \= Z**   
**Value of pInt \= 90**    
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)