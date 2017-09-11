---
title: "방법: 응용 프로그램 도메인에 어셈블리 로드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 934373d61407c8cc19b7d6424898a582880f9c21
ms.openlocfilehash: c319da0f8e6f3cdfb83e659a778136d668699834
ms.contentlocale: ko-kr
ms.lasthandoff: 08/10/2017

---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="50371-102">방법: 응용 프로그램 도메인에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="50371-102">How to: Load Assemblies into an Application Domain</span></span>
<span data-ttu-id="50371-103">응용 프로그램 도메인에 어셈블리를 로드하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-103">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="50371-104"><xref:System.Reflection.Assembly?displayProperty=fullName> 클래스의 `static`(Visual Basic에서는 `Shared`) <xref:System.Reflection.Assembly.Load%2A> 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-104">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=fullName> class.</span></span> <span data-ttu-id="50371-105">어셈블리를 로드할 수 있는 다른 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-105">Other ways assemblies can be loaded include:</span></span>  
  
-   <span data-ttu-id="50371-106"><xref:System.Reflection.Assembly> 클래스의 <xref:System.Reflection.Assembly.LoadFrom%2A> 메서드는 파일 위치가 지정된 경우 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="50371-106">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="50371-107">이 메서드로 어셈블리를 로드하는 경우 다른 로드 컨텍스트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50371-107">Loading assemblies with this method uses a different load context.</span></span>  
  
-   <span data-ttu-id="50371-108"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 및 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 메서드는 리플렉션 전용 컨텍스트에 어셈블리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="50371-108">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="50371-109">이 컨텍스트에 로드된 어셈블리는 검사할 수만 있고 실행할 수 없으므로 다른 플랫폼을 대상으로 하는 어셈블리를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-109">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="50371-110">[방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50371-110">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50371-111">리플렉션 전용 컨텍스트는 .NET Framework 버전 2.0의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="50371-111">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
-   <span data-ttu-id="50371-112"><xref:System.AppDomain> 클래스의 <xref:System.AppDomain.CreateInstance%2A> 및 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>과 같은 메서드는 응용 프로그램 도메인에 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-112">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
-   <span data-ttu-id="50371-113"><xref:System.Type> 클래스의 <xref:System.Type.GetType%2A> 메서드는 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-113">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
-   <span data-ttu-id="50371-114"><xref:System.AppDomain?displayProperty=fullName> 클래스의 <xref:System.AppDomain.Load%2A> 메서드는 어셈블리를 로드할 수 있지만 COM 상호 운용성을 위해 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50371-114">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=fullName> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="50371-115">호출 시 사용된 응용 프로그램 도메인 이외의 응용 프로그램 도메인에 어셈블리를 로드하는 데 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50371-115">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50371-116">.NET Framework 버전 2.0부터 런타임은 현재 로드된 런타임보다 높은 버전 번호를 가진 .NET Framework 버전으로 컴파일된 어셈블리를 로드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-116">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="50371-117">이는 버전 번호의 주 버전 및 부 버전 구성 요소 조합에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50371-117">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="50371-118">로드된 어셈블리의 JIT(Just-In-Time) 컴파일된 코드가 응용 프로그램 도메인 간에 공유되는 방식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50371-118">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="50371-119">자세한 내용은 [응용 프로그램 도메인 및 어셈블리](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50371-119">For more information, see [Application Domains and Assemblies](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50371-120">예제</span><span class="sxs-lookup"><span data-stu-id="50371-120">Example</span></span>  
 <span data-ttu-id="50371-121">다음 코드는 "example.exe" 또는 "example.dll"이라는 어셈블리를 로드 현재 응용 프로그램 도메인에 로드하고, 어셈블리에서 `Example` 형식을 가져온 다음 해당 형식에 대한 매개 변수가 없는 `MethodA` 메서드를 가져와서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50371-121">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="50371-122">로드된 어셈블리에서 정보를 가져오는 방법에 대한 자세한 내용은 [형식 동적 로드 및 사용](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50371-122">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 <span data-ttu-id="50371-123">[!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)] [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)] [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="50371-123">[!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)] [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)] [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50371-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50371-124">See Also</span></span>  
 <span data-ttu-id="50371-125"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A></span><span class="sxs-lookup"><span data-stu-id="50371-125"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A></span></span>   
 <span data-ttu-id="50371-126">[응용 프로그램 도메인으로 프로그래밍](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="50371-126">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 <span data-ttu-id="50371-127">[리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="50371-127">[Reflection](../../../docs/framework/reflection-and-codedom/reflection.md) </span></span>  
 <span data-ttu-id="50371-128">[응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md) </span><span class="sxs-lookup"><span data-stu-id="50371-128">[Using Application Domains](../../../docs/framework/app-domains/use.md) </span></span>  
 <span data-ttu-id="50371-129">[방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) </span><span class="sxs-lookup"><span data-stu-id="50371-129">[How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) </span></span>  
 [<span data-ttu-id="50371-130">응용 프로그램 도메인 및 어셈블리</span><span class="sxs-lookup"><span data-stu-id="50371-130">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)

