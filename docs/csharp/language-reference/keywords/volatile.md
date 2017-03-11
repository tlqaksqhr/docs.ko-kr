---
title: "volatile(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "volatile_CSharpKeyword"
  - "volatile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "volatile 키워드[C#]"
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# volatile(C# 참조)
`volatile` 키워드는 동시에 실행 중인 여러 스레드에 의해 필드가 수정될 수 있음을 나타냅니다.  `volatile`로 선언된 필드에는 단일 스레드를 통한 액세스를 전제로 하는 컴파일러 최적화가 적용되지 않습니다.  이렇게 하면 필드의 값을 항상 최신 상태로 유지할 수 있습니다.  
  
 일반적으로 `volatile` 한정자는 액세스를 serialize할 때 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 문을 사용하지 않고 여러 스레드에서 액세스하는 필드에 사용됩니다.  
  
 `volatile` 키워드는 다음과 같은 형식의 필드에 적용할 수 있습니다.  
  
-   참조 형식  
  
-   안전하지 않은 컨텍스트의 포인터 형식.  포인터 자체는 volatile일 수 있지만 포인터가 가리키는 개체는 volatile일 수 없습니다.  즉, "volatile 개체에 대한 포인터"를 선언할 수 없습니다.  
  
-   sbyte, byte, short, ushort, int, uint, char, float 및 bool 같은 형식  
  
-   다음과 같은 기본 형식 중 하나를 사용하는 열거형 형식: byte, sbyte, short, ushort, int 또는 uint.  
  
-   참조 형식으로 알려진 제네릭 형식 매개 변수  
  
-   <xref:System.IntPtr> 및 <xref:System.UIntPtr>  
  
 volatile 키워드는 클래스 또는 구조체의 필드에만 적용할 수 있습니다.  지역 변수는 `volatile`로 선언할 수 없습니다.  
  
## 예제  
 다음 예제에서는 공용 필드 변수를 `volatile`로 선언하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#24)]  
  
## 예제  
 다음 예제에서는 보조 또는 작업자 스레드를 만들고 기본 스레드와 함께 이 스레드를 병렬로 사용하여 작업 처리를 수행하는 방법을 보여 줍니다.  다중 스레딩에 대한 배경 정보는 [Threading](../Topic/Managed%20Threading.md) 및 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 [!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/csharp/volatile_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)