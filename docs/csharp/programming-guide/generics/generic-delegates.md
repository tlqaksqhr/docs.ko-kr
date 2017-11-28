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
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="0fab2-102">제네릭 대리자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0fab2-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="0fab2-103">[대리자](../../../csharp/language-reference/keywords/delegate.md)는 자체 형식 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fab2-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="0fab2-104">제네릭 대리자를 참조하는 코드는 다음 예제와 같이 제네릭 클래스를 인스턴스화하거나 제네릭 메서드를 호출하는 것과 같은 방법으로 형식 인수를 지정하여 폐쇄형 생성 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fab2-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 <span data-ttu-id="0fab2-105">C# 버전 2.0에는 메서드 그룹 변환이라는 새로운 기능이 있습니다. 이 기능은 제네릭 대리자 형식은 물론 구체적인 대리자 형식에도 적용되며, 이 기능을 사용하여 위 코드 줄을 다음과 같이 간단한 구문으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fab2-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 <span data-ttu-id="0fab2-106">제네릭 클래스 내에 정의된 대리자는 클래스 메서드와 같은 방식으로 제네릭 클래스 형식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fab2-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 <span data-ttu-id="0fab2-107">대리자를 참조하는 코드는 포함 클래스의 형식 인수를 다음과 같이 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab2-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 <span data-ttu-id="0fab2-108">제네릭 대리자는 sender 인수를 강력하게 형식화할 수 있고 더 이상 sender 인수와 <xref:System.Object> 간에 캐스팅하지 않아도 되기 때문에 일반적인 디자인 패턴을 기반으로 하는 이벤트를 정의할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab2-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0fab2-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fab2-109">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="0fab2-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0fab2-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0fab2-111">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="0fab2-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="0fab2-112">제네릭 메서드</span><span class="sxs-lookup"><span data-stu-id="0fab2-112">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
 [<span data-ttu-id="0fab2-113">제네릭 클래스</span><span class="sxs-lookup"><span data-stu-id="0fab2-113">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
 [<span data-ttu-id="0fab2-114">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0fab2-114">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
 [<span data-ttu-id="0fab2-115">대리자</span><span class="sxs-lookup"><span data-stu-id="0fab2-115">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="0fab2-116">제네릭</span><span class="sxs-lookup"><span data-stu-id="0fab2-116">Generics</span></span>](~/docs/standard/generics/index.md)
