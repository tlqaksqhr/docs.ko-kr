---
title: "제네릭의 장점(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "제네릭[C#], 장점"
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# 제네릭의 장점(C# 프로그래밍 가이드)
제네릭을 사용하면 이전 버전의 공용 언어 런타임과 C\# 언어에 적용되었던 제한 사항을 해결할 수 있습니다. 이전 버전에서는 유니버설 기본 형식인 <xref:System.Object>와 형식 사이의 캐스팅을 통해 일반화를 수행했습니다.  제네릭 클래스를 만들면 컴파일 타임에 형식이 안전한 컬렉션을 만들 수 있습니다.  
  
 제네릭이 아닌 컬렉션 클래스를 사용하는 경우의 제한 사항을 보여 주는 예로는 .NET Framework 클래스 라이브러리에서 <xref:System.Collections.ArrayList> 컬렉션 클래스를 사용하는 간단한 프로그램을 작성하는 경우를 들 수 있습니다.  <xref:System.Collections.ArrayList>는 참조나 값 형식을 저장하기 위해 수정하지 않고도 사용할 수 있는 매우 편리한 컬렉션 클래스입니다.  
  
 [!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 그러나 이러한 편리함에는 상응하는 대가가 따릅니다.  <xref:System.Collections.ArrayList>에 추가되는 모든 참조나 값 형식은 <xref:System.Object>에 암시적으로 업캐스팅됩니다.  항목이 값 형식이면 이를 목록에 추가할 때 boxing해야 하고 이를 검색할 때 unboxing해야 합니다.  캐스팅이나 boxing 및 unboxing 작업은 모두 성능을 저하시킵니다. 큰 컬렉션을 반복해야 하는 시나리오에서는 boxing과 unboxing의 영향을 결코 무시할 수 없습니다.  
  
 다른 제한 사항으로는 컴파일 타임에 형식을 검사할 수 없다는 점을 들 수 있습니다. <xref:System.Collections.ArrayList>는 <xref:System.Object>에 모든 항목을 캐스팅하므로 컴파일 타임에 클라이언트 코드가 다음과 같은 작업을 수행하지 못하도록 막을 수 없습니다.  
  
 [!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 유형이 다른 컬렉션을 만드는 경우 규칙을 정확히 따르는 의도적인 선택일지라도 문자열과 `ints`를 단일 <xref:System.Collections.ArrayList>에 결합하면 프로그래밍 오류가 발생할 확률이 더 커지고 이러한 오류는 런타임 이전에 발견할 수 없습니다.  
  
 버전 1.0 및 1.1의 C\# 언어에서는 고유한 형식별 컬렉션을 작성하는 방법으로만 .NET Framework 기본 클래스 라이브러리 컬렉션 클래스에서 코드를 일반화하는 위험을 방지할 수 있었습니다.  물론 이러한 클래스는 여러 데이터 형식에 다시 사용할 수 없으므로 일반화의 이점이 사라지고 저장하려는 각 형식에 대해 클래스를 다시 작성해야만 합니다.  
  
 <xref:System.Collections.ArrayList> 및 기타 유사한 클래스에 실제로 필요한 것은 클라이언트 코드에서 사용하려는 특정 데이터 형식을 인스턴스별로 지정할 수 있는 방법입니다.  이렇게 하면 `T:System.Object`로 업캐스팅할 필요가 없어지고 컴파일러에서 형식을 검사할 수도 있게 됩니다.  즉, <xref:System.Collections.ArrayList>에는 형식 매개 변수가 필요합니다.  제네릭은 바로 이러한 요구 사항을 충족시킵니다.  `N:System.Collections.Generic` 네임스페이스의 제네릭 <xref:System.Collections.Generic.List%601> 컬렉션에서는 컬렉션에 항목을 추가하는 동일한 작업을 다음과 같이 수행할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 클라이언트 코드에서 <xref:System.Collections.ArrayList>와 비교할 때 <xref:System.Collections.Generic.List%601>을 사용하여 유일하게 추가된 구문은 선언과 인스턴스화의 형식 인수입니다.  이와 같이 코딩이 약간 더 복잡해진 대신 <xref:System.Collections.ArrayList>보다 안전하면서도 속도가 훨씬 빠른 목록을 만들 수 있습니다. 이러한 차이는 목록 항목이 값 형식인 경우에 특히 잘 드러납니다.  
  
## 참고 항목  
 <xref:System.Collections.Generic>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)   
 [최상의 컬렉션 방법](http://go.microsoft.com/fwlink/?LinkId=112403)