---
title: "제네릭 소개(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61baf26c9f942a59e3787ca55a2ac6a824410608
ms.sourcegitcommit: 3fd4e718d1bac9769fe0c1dd08ca1b2323ae272b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2018
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="8b181-102">제네릭 소개(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8b181-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="8b181-103">제네릭 클래스 및 메서드는 제네릭이 아닌 클래스 및 메서드에서는 결합할 수 없는 방식으로 재사용성, 형식 안전성 및 효율성을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="8b181-104">제네릭은 컬렉션 및 해당 컬렉션에서 작동하는 메서드에서 가장 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="8b181-105">.NET Framework 클래스 라이브러리 2.0 버전은 여러 가지 새로운 제네릭 기반 컬렉션 클래스가 포함된 새로운 네임스페이스 <xref:System.Collections.Generic>을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="8b181-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 이상을 대상으로 하는 모든 응용 프로그램은 <xref:System.Collections.ArrayList> 같은 이전의 제네릭이 아닌 컬렉션 클래스 대신 새로운 제네릭 컬렉션 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-106">It is recommended that all applications that target the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="8b181-107">자세한 내용은 [.NET Framework 클래스 라이브러리의 제네릭](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b181-107">For more information, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="8b181-108">물론, 사용자 지정 제네릭 형식 및 메서드를 만들어 형식이 안전하고 효율적인 일반화된 솔루션 및 디자인 패턴을 직접 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="8b181-109">다음 코드 예제에서는 데모용으로 간단한 제네릭 연결된 목록 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="8b181-110">대부분의 경우 직접 만드는 대신 .NET Framework 클래스 라이브러리에서 제공하는 <xref:System.Collections.Generic.List%601> 클래스를 사용해야 합니다. 형식 매개 변수 `T`는 일반적으로 구체적인 형식을 사용하여 목록에 저장된 항목의 형식을 나타내는 여러 위치에서 사용되며,</span><span class="sxs-lookup"><span data-stu-id="8b181-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="8b181-111">다음과 같은 방법으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-111">It is used in the following ways:</span></span>  
  
-   <span data-ttu-id="8b181-112">`AddHead` 메서드에서 메서드 매개 변수의 형식.</span><span class="sxs-lookup"><span data-stu-id="8b181-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
-   <span data-ttu-id="8b181-113">중첩 `Node` 클래스에서 `Data` 속성의 반환 형식.</span><span class="sxs-lookup"><span data-stu-id="8b181-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
-   <span data-ttu-id="8b181-114">중첩 클래스에서 private 멤버 `data`의 형식.</span><span class="sxs-lookup"><span data-stu-id="8b181-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="8b181-115">T는 중첩 `Node` 클래스에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="8b181-116">`GenericList<T>`가 `GenericList<int>`와 같이 구체적인 형식으로 인스턴스화되면 `T`가 나타날 때마다 `int`로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 <span data-ttu-id="8b181-117">다음 코드 예제에서는 클라이언트 코드에서 제네릭 `GenericList<T>` 클래스를 사용하여 정수 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="8b181-118">형식 인수를 변경하기만 하면 다음 코드를 쉽게 수정하여 문자열이나 다른 모든 사용자 지정 형식 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b181-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8b181-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b181-119">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="8b181-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8b181-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8b181-121">제네릭</span><span class="sxs-lookup"><span data-stu-id="8b181-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
