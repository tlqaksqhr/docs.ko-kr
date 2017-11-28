---
title: "공변성(Covariance) 및 반공변성(Contravariance)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cc6eb2c4371f69588fd235a0bd3e872b42eb028f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="45032-102">공변성(Covariance) 및 반공변성(Contravariance)(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-102">Covariance and Contravariance (C#)</span></span>
<span data-ttu-id="45032-103">C#에서 공변성(Covariance)과 반공변성(Contravariance)은 배열 형식, 대리자 형식 및 제네릭 형식 인수에 대한 암시적 참조 변환을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="45032-103">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="45032-104">공변성(Covariance)은 할당 호환성을 유지하고 반공변성(Contravariance)은 할당 호환성을 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45032-104">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="45032-105">다음 코드에서는 할당 호환성, 공변성(Covariance) 및 반공변성(Contravariance) 간의 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-105">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```csharp  
// Assignment compatibility.   
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.   
object obj = str;  
  
// Covariance.   
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument   
// is assigned to an object instantiated with a less derived type argument.   
// Assignment compatibility is preserved.   
IEnumerable<object> objects = strings;  
  
// Contravariance.             
// Assume that the following method is in the class:   
// static void SetObject(object o) { }   
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument   
// is assigned to an object instantiated with a more derived type argument.   
// Assignment compatibility is reversed.   
Action<string> actString = actObject;  
```  
  
 <span data-ttu-id="45032-106">배열에 대한 공변성(Covariance)은 더 많이 파생된 형식의 배열을 더 적게 파생된 형식의 배열로 암시적 변환을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="45032-106">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="45032-107">하지만 다음 코드 예제와 같이 이 작업은 형식이 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45032-107">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="45032-108">메서드 그룹에 대한 공변성(Covariance) 및 반공변성(Contravariance) 지원으로 대리자 형식과 메서드 시그니처를 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45032-108">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="45032-109">일치하는 시그니처가 있는 메서드뿐만이 아니라 더 많이 파생된 형식(공변성(covariance))을 반환하는 메서드 또는 대리자 형식에 지정된 것보다 더 적게 파생된 형식(반공변성(contravariance))을 가지고 있는 매개 변수를 수락하는 메서드도 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45032-109">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="45032-110">자세한 내용은 [대리자의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [대리자의 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45032-110">For more information, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="45032-111">다음 코드 예제에서는 메서드 그룹에 대한 공변성(Covariance) 및 반공변성(Contravariance) 지원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-111">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 <span data-ttu-id="45032-112">.NET Framework 4 이상에서 C#는 제네릭 인터페이스 및 대리자의 공변성(Covariance) 및 반공변성(Contravariance)을 지원하고 제네릭 형식 매개 변수를 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45032-112">In .NET Framework 4 or newer C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="45032-113">자세한 내용은 [제네릭 인터페이스의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) 및 [대리자의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45032-113">For more information, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="45032-114">다음 코드 예제에서는 제네릭 인터페이스에 대한 암시적 참조 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-114">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="45032-115">제네릭 매개 변수가 선언된 공변(covariant) 또는 반공변(contravariant)인 경우 제네릭 인터페이스 또는 대리자를 *variant*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="45032-115">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="45032-116">C#에서는 사용자 고유의 variant 인터페이스 및 대리자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45032-116">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="45032-117">자세한 내용은 [Variant 제네릭 인터페이스 만들기(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) 및 [대리자의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45032-117">For more information, see [Creating Variant Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="45032-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="45032-118">Related Topics</span></span>  
  
|<span data-ttu-id="45032-119">제목</span><span class="sxs-lookup"><span data-stu-id="45032-119">Title</span></span>|<span data-ttu-id="45032-120">설명</span><span class="sxs-lookup"><span data-stu-id="45032-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="45032-121">제네릭 인터페이스의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-121">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="45032-122">제네릭 인터페이스의 공분산 및 반공분산에 대해 설명하고 .NET Framework의 Variant 제네릭 인터페이스의 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45032-122">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="45032-123">Variant 제네릭 인터페이스 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-123">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|<span data-ttu-id="45032-124">사용자 지정 variant 인터페이스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-124">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="45032-125">제네릭 컬렉션용 인터페이스의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-125">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="45032-126"><xref:System.Collections.Generic.IEnumerable%601> 및 <xref:System.IComparable%601> 인터페이스의 공변성(Covariance) 및 반공변성(Contravariance) 지원을 통해 코드를 다시 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-126">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="45032-127">대리자의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-127">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|<span data-ttu-id="45032-128">제네릭 및 제네릭이 아닌 대리자의 공변성(Covariance) 및 반공변성(Contravariance)을 설명하고 .NET Framework의 Variant 제네릭 인터페이스의 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45032-128">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="45032-129">대리자의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-129">Using Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|<span data-ttu-id="45032-130">제네릭이 아닌 대리자의 공변성(Covariance) 및 반공변성(Contravariance) 지원을 사용하여 메서드 시그니처를 대리자 형식과 일치시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-130">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="45032-131">Func 및 Action 제네릭 대리자에 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="45032-131">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="45032-132">`Func` 및 `Action` 대리자의 공변성(Covariance) 및 반공변성(Contravariance) 지원을 통해 코드를 다시 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45032-132">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
