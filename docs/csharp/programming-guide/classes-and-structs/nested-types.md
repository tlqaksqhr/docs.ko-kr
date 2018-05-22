---
title: 중첩 형식(C# 프로그래밍 가이드)
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 57356fbf4bff218932d1f1b4c62532f10c175757
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="nested-types-c-programming-guide"></a>중첩 형식(C# 프로그래밍 가이드)
[클래스](../../../csharp/language-reference/keywords/class.md) 또는 [구조체](../../../csharp/language-reference/keywords/struct.md) 내에서 선언된 형식을 중첩 형식이라고 합니다. 예:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
외부 형식이 클래스 또는 구조체인지와 관계없이 중첩 형식은 기본적으로 [private](../../../csharp/language-reference/keywords/private.md)로 설정됩니다. 포함하는 형식에서만 액세스할 수 있습니다. 앞의 예제에서 `Nested` 클래스는 외부 형식에서 액세스할 수 없습니다. 

다음과 같이 [액세스 한정자](../../language-reference/keywords/access-modifiers.md)를 지정하여 중첩 형식의 접근성을 정의할 수도 있습니다.

- **클래스**의 중첩 형식은 [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) 또는 [private protected](../../../csharp/language-reference/keywords/private-protected.md)일 수 있습니다. 

   그러나 [sealed 클래스](../../language-reference/keywords/sealed.md) 내에서 `protected`, `protected internal` 또는 `private protected` 중첩 클래스를 정의하면 컴파일러 경고 [CS0628](../../misc/cs0628.md), “sealed 클래스에 새 protected 멤버가 선언되었습니다.”가 생성됩니다.
  
- **구조체**의 중첩 형식은 [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 [private](../../../csharp/language-reference/keywords/private.md)일 수 있습니다.
  
다음 예제에서는 `Nested` 클래스를 public으로 설정합니다.
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 중첩 형식(내부 형식)은 이 형식을 포함하고 있는 형식(외부 형식)에 액세스할 수 있습니다. 포함하는 형식에 액세스하려면 중첩 형식의 생성자에 인수로 전달합니다. 예:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 중첩 형식은 이 형식을 포함하는 형식에 액세스할 수 있는 모든 멤버에 액세스할 수 있습니다. 또한 상속 및 보호된 멤버를 포함하여 외부 형식의 개인 및 보호된 멤버에 액세스할 수 있습니다.  
  
 위 선언에서 `Nested` 클래스의 전체 이름은 `Container.Nested`입니다. 이 이름은 다음과 같이 중첩된 클래스의 새 인스턴스를 만드는 데 사용됩니다.  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)
