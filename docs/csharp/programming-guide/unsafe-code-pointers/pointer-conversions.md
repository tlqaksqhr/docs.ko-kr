---
title: "포인터 변환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "포인터[C#], 변환"
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 포인터 변환(C# 프로그래밍 가이드)
다음 표에서는 미리 정의된 암시적 포인터 변환을 보여 줍니다.  메서드 호출, 할당문 등 많은 경우에 암시적 변환이 발생할 수 있습니다.  
  
## 암시적 포인터 변환  
  
|From|To|  
|----------|--------|  
|모든 포인터 형식|void\*|  
|null|모든 포인터 형식|  
  
 암시적 변환이 불가능한 경우에 변환을 수행하려면 캐스트 식을 통해 명시적 변환을 사용합니다.  다음 표에서는 이러한 변환을 보여 줍니다.  
  
## 명시적 포인터 변환  
  
|From|To|  
|----------|--------|  
|모든 포인터 형식|임의의 다른 포인터 형식|  
|sbyte, byte, short, ushort, int, uint, long 또는 ulong|모든 포인터 형식|  
|모든 포인터 형식|sbyte, byte, short, ushort, int, uint, long 또는 ulong|  
  
## 예제  
 다음 예제에서는 `int`에 대한 포인터를 `byte`에 대한 포인터로 변환합니다.  포인터는 변수의 선두 주소 바이트를 가리키게 됩니다.  결과 포인터를 `int`의 크기인 4바이트까지 연속적으로 증가시키면 변수의 나머지 바이트를 표시할 수 있습니다.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)