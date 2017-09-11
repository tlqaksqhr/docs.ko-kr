---
title: AttributeUsage(C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c008c1a696e93bc3b756a926a046aa5a6942bc10
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="attributeusage-c"></a><span data-ttu-id="84d50-102">AttributeUsage(C#)</span><span class="sxs-lookup"><span data-stu-id="84d50-102">AttributeUsage (C#)</span></span>
<span data-ttu-id="84d50-103">사용자 지정 특성 클래스를 사용하는 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="84d50-104">`AttributeUsage`는 새 특성 적용 방법을 제어하기 위해 사용자 지정 특성 정의에 적용할 수 있는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="84d50-105">기본 설정은 명시적으로 적용될 경우 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-105">The default settings look like this when applied explicitly:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="84d50-106">이 예제에서 `NewAttribute` 클래스는 모든 특성 가능 코드 엔터티에 적용될 수 있지만 각 엔터티에 한 번만 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="84d50-107">이 특성은 기본 클래스에 적용될 때 파생 클래스가 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="84d50-108">`AllowMultiple` 및 `Inherited` 인수는 선택 사항이므로 이 코드에 미치는 영향은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="84d50-109">첫 번째 `AttributeUsage` 인수는 <xref:System.AttributeTargets> 열거형의 요소가 하나 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="84d50-110">다음과 같이 OR 연산자를 사용하여 여러 대상 형식을 함께 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 <span data-ttu-id="84d50-111">`AllowMultiple` 인수를 `true`로 설정하면 다음과 같이 결과 특성을 단일 엔터티에 두 번 이상 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 <span data-ttu-id="84d50-112">이 경우 `AllowMultiple`이 `true`로 설정되므로 `MultiUseAttr`를 반복적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="84d50-113">여러 특성을 적용하기 위해 표시된 두 형식이 모두 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="84d50-114">`Inherited`를 `false`로 설정하면 특성이 지정된 클래스에서 파생된 클래스가 특성을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="84d50-115">예:</span><span class="sxs-lookup"><span data-stu-id="84d50-115">For example:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 <span data-ttu-id="84d50-116">이 경우 `Attr1`은 상속을 통해 `DClass`에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d50-117">주의</span><span class="sxs-lookup"><span data-stu-id="84d50-117">Remarks</span></span>  
 <span data-ttu-id="84d50-118">`AttributeUsage` 특성은 단일 사용 특성입니다. 같은 클래스에 두 번 이상 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="84d50-119">`AttributeUsage`는 <xref:System.AttributeUsageAttribute>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="84d50-120">자세한 내용은 [리플렉션을 사용하여 특성 액세스(C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84d50-120">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84d50-121">예제</span><span class="sxs-lookup"><span data-stu-id="84d50-121">Example</span></span>  
 <span data-ttu-id="84d50-122">다음 예제에서는 `AttributeUsage` 특성에 대한 `Inherited` 및 `AllowMultiple`의 영향과 클래스에 적용되는 사용자 지정 특성을 열거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84d50-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a><span data-ttu-id="84d50-123">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="84d50-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="84d50-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84d50-124">See Also</span></span>  
 <span data-ttu-id="84d50-125"><xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="84d50-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="84d50-126"><xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="84d50-126"><xref:System.Reflection></span></span>   
 <span data-ttu-id="84d50-127">[C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="84d50-127">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="84d50-128">[특성](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="84d50-128">[Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
 <span data-ttu-id="84d50-129">[리플렉션(C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="84d50-129">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 <span data-ttu-id="84d50-130">[특성](../../../../csharp/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="84d50-130">[Attributes](../../../../csharp/programming-guide/concepts/attributes/index.md) </span></span>  
 <span data-ttu-id="84d50-131">[사용자 지정 특성 만들기(C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="84d50-131">[Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
 [<span data-ttu-id="84d50-132">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="84d50-132">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

