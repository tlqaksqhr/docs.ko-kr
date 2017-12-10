---
title: "특성(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f9fc23cf7afbd28f0c9ae438cbce298cbf362fbd
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="attributes-c"></a><span data-ttu-id="b51e0-102">특성(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-102">Attributes (C#)</span></span>
<span data-ttu-id="b51e0-103">특성은 메타데이터 또는 선언적 정보를 코드(어셈블리, 형식, 메서드, 속성 등)에 연결하는 강력한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="b51e0-104">특성이 프로그램 엔터티와 연결되면 *리플렉션*이라는 기법을 사용하여 런타임에 특성이 쿼리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="b51e0-105">자세한 내용은 [리플렉션(C#)](../../../../csharp/programming-guide/concepts/reflection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-105">For more information, see [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="b51e0-106">특성에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="b51e0-107">특성은 프로그램에 메타데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="b51e0-108">*메타데이터*는 프로그램에 정의된 형식에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="b51e0-109">모든 .NET 어셈블리에는 어셈블리에 정의된 형식 및 형식 멤버를 설명하는 지정된 메타데이터 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="b51e0-110">필요한 추가 정보를 지정하는 사용자 지정 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="b51e0-111">자세한 내용은 [사용자 지정 특성 만들기(C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-111">For more information, see, [Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="b51e0-112">전체 어셈블리, 모듈 또는 좀 더 작은 프로그램 요소(예: 클래스 및 속성)에 하나 이상의 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="b51e0-113">메서드 및 속성의 경우와 같은 방식으로 특성은 인수를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="b51e0-114">프로그램은 리플렉션을 사용하여 자체 메타데이터 또는 다른 프로그램의 메타데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="b51e0-115">자세한 내용은 [리플렉션을 사용하여 특성 액세스(C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-115">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="b51e0-116">특성 사용</span><span class="sxs-lookup"><span data-stu-id="b51e0-116">Using Attributes</span></span>  
 <span data-ttu-id="b51e0-117">특정 특성이 유효한 선언 형식을 제한할 수  있지만 거의 모든 선언에 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="b51e0-118">C#에서 특성 이름을 대괄호([])로 묶어 적용하는 엔터티의 선언 위에 배치하여 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-118">In C#, you specify an attribute by placing the name of the attribute, enclosed in square brackets ([]), above the declaration of the entity to which it applies.</span></span>  
  
 <span data-ttu-id="b51e0-119">이 예제에서 <xref:System.SerializableAttribute> 특성은 클래스에 특정 특성을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 <span data-ttu-id="b51e0-120"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 사용하는 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 <span data-ttu-id="b51e0-121">둘 이상의 특성을 하나의 선언에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-121">More than one attribute can be placed on a declaration:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 <span data-ttu-id="b51e0-122">지정된 엔터티에 대해 일부 특성을 두 번 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="b51e0-123">이러한 다용도 특성의 예로 <xref:System.Diagnostics.ConditionalAttribute>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="b51e0-124">규칙에 따라 모든 특성 이름은 .NET Framework의 다른 항목과 구분하기 위해 단어 "Attribute"로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="b51e0-125">그러나 코드에서 특성을 사용하는 경우 특성 접미사를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="b51e0-126">예를 들어 `[DllImport]`는 `[DllImportAttribute]`와 같지만 `DllImportAttribute`는 .NET Framework에서 특성의 실제 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="b51e0-127">특성 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b51e0-127">Attribute Parameters</span></span>  
 <span data-ttu-id="b51e0-128">많은 특성에는 매개 변수를 위치, 명명되지 않은 또는 명명된 상태의 매개 변수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="b51e0-129">모든 위치 매개 변수는 특정 순서로 지정해야 하며 생략할 수 없습니다. 명명된 매개 변수는 선택적이며 순서에 관계 없이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-129">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="b51e0-130">위치 매개 변수가 가장 먼저 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-130">Positional parameters are specified first.</span></span> <span data-ttu-id="b51e0-131">예를 들어 다음 세 가지 특성은 동급입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-131">For example, these three attributes are equivalent:</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 <span data-ttu-id="b51e0-132">첫 번째 매개 변수인 DLL 이름은 위치 매개 변수이므로 항상 맨 먼저 오고 나머지 매개 변수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-132">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="b51e0-133">이 경우 명명된 두 매개 변수는 기본적으로 false이므로 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-133">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="b51e0-134">기본 매개 변수 값에 대한 자세한 내용은 개별 특성의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-134">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="b51e0-135">특성 대상</span><span class="sxs-lookup"><span data-stu-id="b51e0-135">Attribute Targets</span></span>  
 <span data-ttu-id="b51e0-136">특성의 *대상*은 특성이 적용되는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-136">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="b51e0-137">예를 들어 특성은 클래스, 특정 메서드 또는 전체 어셈블리에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-137">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="b51e0-138">기본적으로 특성은 그 앞에 오는 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-138">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="b51e0-139">하지만 특성이 메서드, 해당 매개 변수 또는 해당 반환 값 중 어디에 적용될지를 명시적으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-139">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="b51e0-140">특성 대상을 명시적으로 식별하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-140">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```csharp  
[target : attribute-list]  
```  
  
 <span data-ttu-id="b51e0-141">가능한 `target` 값 목록은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-141">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="b51e0-142">대상 값</span><span class="sxs-lookup"><span data-stu-id="b51e0-142">Target value</span></span>|<span data-ttu-id="b51e0-143">적용 대상</span><span class="sxs-lookup"><span data-stu-id="b51e0-143">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="b51e0-144">전체 어셈블리</span><span class="sxs-lookup"><span data-stu-id="b51e0-144">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="b51e0-145">현재 어셈블리 모듈</span><span class="sxs-lookup"><span data-stu-id="b51e0-145">Current assembly module</span></span>|  
|`field`|<span data-ttu-id="b51e0-146">클래스 또는 구조체의 필드</span><span class="sxs-lookup"><span data-stu-id="b51e0-146">Field in a class or a struct</span></span>|  
|`event`|<span data-ttu-id="b51e0-147">이벤트</span><span class="sxs-lookup"><span data-stu-id="b51e0-147">Event</span></span>|  
|`method`|<span data-ttu-id="b51e0-148">메서드 또는 `get` 및 `set` 속성 접근자</span><span class="sxs-lookup"><span data-stu-id="b51e0-148">Method or `get` and `set` property accessors</span></span>|  
|`param`|<span data-ttu-id="b51e0-149">메서드 매개 변수 또는 `set` 속성 접근자 매개 변수</span><span class="sxs-lookup"><span data-stu-id="b51e0-149">Method parameters or `set` property accessor parameters</span></span>|  
|`property`|<span data-ttu-id="b51e0-150">속성</span><span class="sxs-lookup"><span data-stu-id="b51e0-150">Property</span></span>|  
|`return`|<span data-ttu-id="b51e0-151">메서드, 속성 인덱서 또는 `get` 속성 접근자의 반환 값</span><span class="sxs-lookup"><span data-stu-id="b51e0-151">Return value of a method, property indexer, or `get` property accessor</span></span>|  
|`type`|<span data-ttu-id="b51e0-152">구조체, 클래스, 인터페이스, 열거형 또는 대리자</span><span class="sxs-lookup"><span data-stu-id="b51e0-152">Struct, class, interface, enum, or delegate</span></span>|  
  
 <span data-ttu-id="b51e0-153">다음 예제에서는 어셈블리와 모듈에 특성을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-153">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="b51e0-154">자세한 내용은 [공통 특성(C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-154">For more information, see [Common Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 <span data-ttu-id="b51e0-155">다음 예제에서는 C#에서 메서드, 메서드 매개 변수 및 메서드 반환 값에 특성을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-155">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  <span data-ttu-id="b51e0-156">`SomeAttr`이 정의되는 대상이 유효한지에 상관없이, 반환 값에만 적용하도록 `SomeAttr`이 정의된 경우에도 `return` 대상을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-156">Regardless of the targets on which `SomeAttr` is defined to be valid, the `return` target has to be specified, even if `SomeAttr` were defined to apply only to return values.</span></span> <span data-ttu-id="b51e0-157">즉, 컴파일러는 모호한 특성 대상을 확인하기 위해 `AttributeUsage` 정보를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-157">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="b51e0-158">자세한 내용은 [AttributeUsage(C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-158">For more information, see [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span></span>  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="b51e0-159">특성의 일반적인 용도</span><span class="sxs-lookup"><span data-stu-id="b51e0-159">Common Uses for Attributes</span></span>  
 <span data-ttu-id="b51e0-160">다음 목록에는 코드에서 특성이 사용되는 일반적인 경우가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e0-160">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="b51e0-161">SOAP 프로토콜을 통해 메서드를 호출할 수 있음을 나타내기 위해 웹 서비스에서 `WebMethod` 특성을 사용하여 메서드에 표시.</span><span class="sxs-lookup"><span data-stu-id="b51e0-161">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="b51e0-162">자세한 내용은 <xref:System.Web.Services.WebMethodAttribute>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b51e0-162">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="b51e0-163">네이티브 코드와 상호 운용될 경우 메서드 매개 변수를 마샬링하는 방법 설명.</span><span class="sxs-lookup"><span data-stu-id="b51e0-163">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="b51e0-164">자세한 내용은 <xref:System.Runtime.InteropServices.MarshalAsAttribute>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b51e0-164">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="b51e0-165">클래스, 메서드 및 인터페이스에 대한 COM 속성 설명</span><span class="sxs-lookup"><span data-stu-id="b51e0-165">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="b51e0-166"><xref:System.Runtime.InteropServices.DllImportAttribute> 클래스를 사용하는 비관리 코드 호출</span><span class="sxs-lookup"><span data-stu-id="b51e0-166">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="b51e0-167">제목, 버전, 설명 또는 상표를 기준으로 어셈블리 설명</span><span class="sxs-lookup"><span data-stu-id="b51e0-167">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="b51e0-168">지속성을 위해 serialize할 클래스의 멤버 설명</span><span class="sxs-lookup"><span data-stu-id="b51e0-168">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="b51e0-169">XML serialization를 위해 클래스 멤버 및 XML 노드 간을 매핑하는 방법 설명</span><span class="sxs-lookup"><span data-stu-id="b51e0-169">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="b51e0-170">메서드에 대한 보안 요구 사항 설명</span><span class="sxs-lookup"><span data-stu-id="b51e0-170">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="b51e0-171">보안을 적용하는 데 사용되는 특징 지정</span><span class="sxs-lookup"><span data-stu-id="b51e0-171">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="b51e0-172">코드를 쉽게 디버그할 수 있도록 하기 위해 JIT(Just-In-Time) 컴파일러를 통해 최적화 제어</span><span class="sxs-lookup"><span data-stu-id="b51e0-172">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="b51e0-173">메서드 호출자에 대한 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="b51e0-173">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b51e0-174">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b51e0-174">Related Sections</span></span>  
 <span data-ttu-id="b51e0-175">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e0-175">For more information, see:</span></span>  
  
-   [<span data-ttu-id="b51e0-176">사용자 지정 특성 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-176">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [<span data-ttu-id="b51e0-177">리플렉션을 사용하여 특성 액세스(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-177">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [<span data-ttu-id="b51e0-178">방법: 특성을 사용하여 C/C++ 공용 구조체 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-178">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="b51e0-179">공통 특성(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-179">Common Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [<span data-ttu-id="b51e0-180">호출자 정보(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-180">Caller Information (C#)</span></span>](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="b51e0-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b51e0-181">See Also</span></span>  
 [<span data-ttu-id="b51e0-182">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b51e0-182">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b51e0-183">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="b51e0-183">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="b51e0-184">특성</span><span class="sxs-lookup"><span data-stu-id="b51e0-184">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)
