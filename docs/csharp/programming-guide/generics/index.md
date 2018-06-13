---
title: 제네릭(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 8f412366072c81b8aaca94829e0aa214f356200d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333816"
---
# <a name="generics-c-programming-guide"></a>제네릭(C# 프로그래밍 가이드)
제네릭이 C# 언어 및 CLR(공용 언어 런타임)의 버전 2.0에 추가되었습니다. 제네릭은 .NET Framework에 클라이언트 코드에서 클래스 또는 메서드를 선언하고 인스턴스화할 때까지 하나 이상의 형식 사양을 따르는 클래스 및 메서드를 디자인할 수 있도록 만드는 형식 매개 변수 개념을 도입합니다. 예를 들어 제네릭 형식 매개 변수 T를 사용하여 여기에 표시된 것처럼, 다른 클라이언트 코드에서 런타임 캐스팅 또는 boxing 작업에 대한 비용이나 위험을 발생하지 않고 사용할 수 있는 단일 클래스를 작성할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## <a name="generics-overview"></a>제네릭 개요  
  
-   제네릭 형식을 사용하여 코드 재사용, 형식 안전성 및 성능을 최대화합니다.  
  
-   가장 일반적으로 제네릭은 컬렉션 클래스를 만드는 데 사용됩니다.  
  
-   .NET Framework 클래스 라이브러리에는 <xref:System.Collections.Generic> 네임스페이스에 여러 가지 새로운 제네릭 컬렉션 클래스가 포함됩니다. 이러한 제네릭 컬렉션 클래스는 가능할 때마다 <xref:System.Collections> 네임스페이스의 <xref:System.Collections.ArrayList>처럼 클래스 대신 사용되어야 합니다.  
  
-   사용자 고유의 제네릭 인터페이스, 클래스, 메서드, 이벤트 및 대리자를 만들 수 있습니다.  
  
-   제네릭 클래스는 특정 데이터 형식의 메서드에 액세스할 수 있도록 제한될 수 있습니다.  
  
-   제네릭 데이터 형식에 사용되는 형식에 대한 정보는 리플렉션을 사용하여 런타임 시 얻을 수 있습니다.  
  
## <a name="related-sections"></a>관련 단원  
 추가 정보  
  
-   [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [제네릭의 장점](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [제네릭 형식 매개 변수](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [제네릭 인터페이스](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [C++ 템플릿과 C# 제네릭의 차이점](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [제네릭 및 리플렉션](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [런타임의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 자세한 내용은 [C# 언어 사양](../../../csharp/language-reference/language-specification/index.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [유형](../../../csharp/programming-guide/types/index.md)  
 [\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)  
 [\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)  
 [.NET의 제네릭](../../../standard/generics/index.md)  