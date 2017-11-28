---
title: "제네릭 대리자(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1377723f18d6dd0e984538b530acbc7aa8d52feb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generic-delegates-c-programming-guide"></a>제네릭 대리자(C# 프로그래밍 가이드)
[대리자](../../../csharp/language-reference/keywords/delegate.md)는 자체 형식 매개 변수를 정의할 수 있습니다. 제네릭 대리자를 참조하는 코드는 다음 예제와 같이 제네릭 클래스를 인스턴스화하거나 제네릭 메서드를 호출하는 것과 같은 방법으로 형식 인수를 지정하여 폐쇄형 생성 형식을 만들 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 C# 버전 2.0에는 메서드 그룹 변환이라는 새로운 기능이 있습니다. 이 기능은 제네릭 대리자 형식은 물론 구체적인 대리자 형식에도 적용되며, 이 기능을 사용하여 위 코드 줄을 다음과 같이 간단한 구문으로 작성할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 제네릭 클래스 내에 정의된 대리자는 클래스 메서드와 같은 방식으로 제네릭 클래스 형식 매개 변수를 사용할 수 있습니다.  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 대리자를 참조하는 코드는 포함 클래스의 형식 인수를 다음과 같이 지정해야 합니다.  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 제네릭 대리자는 sender 인수를 강력하게 형식화할 수 있고 더 이상 sender 인수와 <xref:System.Object> 간에 캐스팅하지 않아도 되기 때문에 일반적인 디자인 패턴을 기반으로 하는 이벤트를 정의할 때 특히 유용합니다.  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)  
 [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)  
 [제네릭 인터페이스](../../../csharp/programming-guide/generics/generic-interfaces.md)  
 [대리자](../../../csharp/programming-guide/delegates/index.md)  
 [제네릭](~/docs/standard/generics/index.md)
