---
title: 사용자 지정 특성 액세스
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aafd1586068dcd7aaf4a72ef5454e3a2698ccd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="3906c-102">사용자 지정 특성 액세스</span><span class="sxs-lookup"><span data-stu-id="3906c-102">Accessing Custom Attributes</span></span>
<span data-ttu-id="3906c-103">특성이 프로그램 요소와 연결된 후 리플렉션을 사용하여 특성의 존재 및 값을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-103">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="3906c-104">.NET Framework 버전 1.0 및 1.1에서 사용자 지정 특성은 실행 컨텍스트에서 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-104">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="3906c-105">.NET Framework 버전 2.0에서는 실행을 위해 로드할 수 없는 코드를 검사하는 데 사용할 수 있는 새로운 로드 컨텍스트인 리플렉션 전용 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-105">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="3906c-106">리플렉션 전용 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="3906c-106">The Reflection-Only Context</span></span>  
 <span data-ttu-id="3906c-107">리플렉션 전용 컨텍스트로 로드된 코드는 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-107">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="3906c-108">즉, 생성자를 실행할 필요가 없으므로 사용자 지정 특성의 인스턴스를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-108">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="3906c-109">리플렉션 전용 컨텍스트에서 사용자 지정 특성을 로드하고 검사하려면 <xref:System.Reflection.CustomAttributeData> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-109">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="3906c-110">static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> 메서드의 적절한 오버로드를 사용하여 이 클래스의 인스턴스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-110">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3906c-111">[방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3906c-111">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="3906c-112">실행 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="3906c-112">The Execution Context</span></span>  
 <span data-ttu-id="3906c-113">실행 컨텍스트에서 특성을 쿼리하는 기본 리플렉션 메서드는 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> 및 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-113">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3906c-114">사용자 지정 특성의 접근성은 연결된 어셈블리를 기준으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-114">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="3906c-115">이 확인은 사용자 지정 특성이 연결된 어셈블리의 형식에 대한 메서드가 사용자 지정 특성의 생성자를 호출할 수 있는지 확인하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-115">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="3906c-116"><xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> 같은 메서드는 형식 인수의 표시 유형 및 접근성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-116">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="3906c-117">사용자 정의 형식이 포함된 어셈블리의 코드만 **GetCustomAttributes**를 사용하여 해당 형식의 사용자 지정 특성을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-117">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="3906c-118">다음 C# 예제는 일반적인 사용자 지정 특성 디자인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-118">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="3906c-119">이 예제는 런타임 사용자 지정 특성 리플렉션 모델을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-119">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="3906c-120">런타임에서 **GetLanguage** 메서드에 연결된 public 사용자 지정 특성 유형 <xref:System.ComponentModel.DescriptionAttribute>에 대한 사용자 지정 특성을 검색하려고 시도하는 경우에는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-120">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1.  <span data-ttu-id="3906c-121">런타임은 **Type.GetCustomAttributes**(*type* 형식)에 대한 형식 인수 **DescriptionAttribute**가 public이고 이에 따라 표시되고 액세스 가능한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-121">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2.  <span data-ttu-id="3906c-122">런타임은 **DescriptionAttribute**에서 파생된 사용자 정의 형식 **MyDescriptionAttribute**가 **GetLanguage**() 메서드에 연결된 경우 **System.Web.DLL** 어셈블리 내에서 표시되고 액세스 가능한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-122">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3.  <span data-ttu-id="3906c-123">런타임은 **MyDescriptionAttribute**의 생성자가 **System.Web.DLL** 어셈블리 내에서 표시되고 액세스 가능한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-123">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4.  <span data-ttu-id="3906c-124">런타임은 사용자 지정 특성 매개 변수를 사용하여 **MyDescriptionAttribute**의 생성자를 호출하고 새 개체를 호출자로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-124">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="3906c-125">사용자 지정 특성 리플렉션 모델에서는 형식이 정의된 어셈블리 외부에서 사용자 정의 형식의 인스턴스가 누수될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-125">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="3906c-126">이것은 **RuntimeMethodInfo** 개체의 배열을 반환하는 <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>와 같이 사용자 정의 형식의 인스턴스를 반환하는 런타임 시스템 라이브러리의 멤버와 다르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-126">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="3906c-127">클라이언트가 사용자 정의 사용자 지정 특성 유형 관련 정보를 검색하지 않게 하려면 유형의 멤버를 public이 아닌 멤버로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-127">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="3906c-128">다음 예제에서는 리플렉션을 사용하여 사용자 지정 특성에 대한 액세스 권한을 얻는 기본적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3906c-128">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3906c-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3906c-129">See Also</span></span>  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3906c-130">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="3906c-130">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)  
 [<span data-ttu-id="3906c-131">리플렉션의 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3906c-131">Security Considerations for Reflection</span></span>](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)
