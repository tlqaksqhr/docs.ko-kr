---
title: volatile(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 64bd5ce7d7dfe3265c3c645467493ab7d8792172
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936880"
---
# <a name="volatile-c-reference"></a>volatile(C# 참조)
`volatile` 키워드는 동시에 실행되는 여러 스레드에 의해 필드가 수정될 수 있음을 나타냅니다. `volatile`로 선언된 필드에는 단일 스레드에 의한 액세스를 가정하는 컴파일러 최적화가 적용되지 않습니다. 이러한 제한 사항은 모든 스레드가 수행된 순서대로 다른 스레드가 휘발성 쓰기를 수행하게 합니다. 모든 실행 스레드에서처럼 휘발성 쓰기의 단일 순서가 모두 보장되는 것은 아닙니다.  
  
 `volatile` 한정자는 대개 여러 스레드가 액세스하는 필드에 사용되며, 액세스를 serialize하는 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 문을 사용하지 않습니다.  
  
 `volatile` 키워드는 다음 형식의 필드에 적용될 수 있습니다.  
  
-   참조 형식.  
  
-   포인터 형식(안전하지 않은 컨텍스트에서). 포인터 자체는 volatile이 될 수 있지만, 포인터가 가리키는 개체는 volatile이 될 수 없습니다. 즉, "pointer to volatile"을 선언할 수 없습니다.  
  
-   sbyte, byte, short, ushort, int, uint, char, float, bool 등의 형식.  
  
-   byte, sbyte, short, ushort, int 또는 uint 기본 형식 중 하나를 포함하는 열거형 형식.  
  
-   참조 형식으로 알려진 제네릭 형식 매개 변수.  
  
-   <xref:System.IntPtr>와 <xref:System.UIntPtr>을 참조하세요.  
  
 Volatile 키워드는 클래스 또는 구조체의 필드에만 적용할 수 있습니다. 지역 변수는 `volatile`로 선언할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 공용 필드 변수를 `volatile`로 선언하는 방법을 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a>예  
 다음 예제에서는 보조 또는 작업자 스레드를 만들어 기본 스레드와 병렬로 처리하는 데 사용하는 방법을 보여줍니다. 다중 스레딩에 대한 배경 정보는 [관리되는 스레딩](../../../standard/threading/index.md) 및 [스레딩(C#)](../../programming-guide/concepts/threading/index.md)을 참조하세요.  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [한정자](../../../csharp/language-reference/keywords/modifiers.md)
