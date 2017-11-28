---
title: "제네릭의 장점(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9f46a328208b49aa33130a020e1a85b6f7aa7d97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="benefits-of-generics-c-programming-guide"></a>제네릭의 장점(C# 프로그래밍 가이드)
제네릭은 형식을 유니버설 기본 형식 <xref:System.Object>으로/에서 캐스팅하여 일반화가 수행되는 이전 버전의 공용 언어 런타임 및 C# 언어의 제한 사항에 대한 솔루션을 제공합니다. 제네릭 클래스를 만들면 컴파일 시간에 형식이 안전한 컬렉션을 만들 수 있습니다.  
  
 .NET Framework 클래스 라이브러리의 <xref:System.Collections.ArrayList> 컬렉션 클래스를 사용하는 간단한 프로그램을 작성하면 제네릭이 아닌 컬렉션 클래스를 사용할 경우의 제한 사항을 보여 줄 수 있습니다. <xref:System.Collections.ArrayList>는 수정하지 않고 참조 형식이나 값 형식을 저장하는 데 사용할 수 있는 매우 편리한 컬렉션 클래스입니다.  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 하지만 이 편리함에는 대가가 따릅니다. <xref:System.Collections.ArrayList>에 추가된 모든 참조 형식이나 값 형식이 암시적으로 <xref:System.Object>로 업캐스팅됩니다. 항목이 값 형식이면 목록에 추가될 때 boxing하고 검색될 때 unboxing해야 합니다. 캐스팅과 boxing 및 unboxing 작업은 모두 성능을 저하시키므로 큰 컬렉션을 반복해야 하는 시나리오에서는 boxing 및 unboxing이 큰 영향을 줄 수 있습니다.  
  
 다른 제한 사항은 컴파일 시간 형식 검사가 없다는 것입니다. <xref:System.Collections.ArrayList>가 모든 항목을 <xref:System.Object>로 캐스팅하기 때문에 컴파일 시간에는 클라이언트 코드에서 다음과 같은 작업을 수행하지 않도록 차단할 방법이 없습니다.  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 완벽하게 허용되고, 다른 유형의 컬렉션을 만드는 경우 의도적일 때도 있지만 단일 <xref:System.Collections.ArrayList>에 문자열과 `ints`를 함께 사용하면 프로그래밍 오류가 발생할 가능성이 크며 이 오류는 런타임 시까지 검색되지 않습니다.  
  
 C# 언어의 버전 1.0 및 1.1에서는 사용자 고유의 형식별 컬렉션을 작성해야만 .NET Framework 기본 클래스 라이브러리 컬렉션 클래스에 일반화된 코드가 포함될 위험을 방지할 수 있습니다. 물론, 이러한 클래스는 둘 이상의 데이터 형식에 다시 사용할 수 없기 때문에 일반화의 이점이 손실되며 저장할 각 형식에 대한 클래스를 다시 작성해야 합니다.  
  
 <xref:System.Collections.ArrayList> 및 다른 유사한 클래스에 실제로 필요한 것은 클라이언트 코드에서 사용할 특정 데이터 형식을 인스턴스 단위로 지정할 수 있는 방법입니다. 그러면 `T:System.Object`로 업캐스팅할 필요가 없으며 컴파일러가 형식을 검사할 수 있습니다. 즉, <xref:System.Collections.ArrayList>에 형식 매개 변수가 필요합니다. 제네릭은 바로 이것을 제공합니다. 제네릭 <xref:System.Collections.Generic.List%601> 컬렉션의 `N:System.Collections.Generic` 네임스페이스에서 컬렉션에 항목을 추가하는 동일한 작업은 다음과 비슷합니다.  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 클라이언트 코드의 경우 <xref:System.Collections.ArrayList>에 해당하는 <xref:System.Collections.Generic.List%601>로 추가된 유일한 구문은 선언 및 인스턴스화의 형식 인수입니다. 코딩이 약간 더 복잡하지만 <xref:System.Collections.ArrayList>보다 안전할 뿐 아니라 특히 목록 항목이 값 형식인 경우 훨씬 더 빠른 목록을 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
 [컬렉션 모범 사례](http://go.microsoft.com/fwlink/?LinkId=112403)
