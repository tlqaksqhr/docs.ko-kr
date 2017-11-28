---
title: "어셈블리 이름"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 624cc6ad264f32b9a43917d9bae751f57b4421a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-names"></a><span data-ttu-id="cb7ca-102">어셈블리 이름</span><span class="sxs-lookup"><span data-stu-id="cb7ca-102">Assembly Names</span></span>
<span data-ttu-id="cb7ca-103">어셈블리 이름은 메타데이터에 저장되고 어셈블리 범위 및 응용 프로그램에 의한 사용에 상당한 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-103">An assembly's name is stored in metadata and has a significant impact on the assembly's scope and use by an application.</span></span> <span data-ttu-id="cb7ca-104">강력한 이름의 어셈블리에는 어셈블리의 이름, 문화권, 공개 키 및 버전 번호가 포함된 정규화된 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-104">A strong-named assembly has a fully qualified name that includes the assembly's name, culture, public key, and version number.</span></span> <span data-ttu-id="cb7ca-105">이 이름을 보통 표시 이름이라고 하고 로드된 어셈블리의 경우 <xref:System.Reflection.Assembly.FullName%2A> 속성을 사용하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-105">This is frequently referred to as the display name, and for loaded assemblies can be obtained by using the <xref:System.Reflection.Assembly.FullName%2A> property.</span></span>  
  
 <span data-ttu-id="cb7ca-106">런타임은 이 정보를 사용하여 어셈블리를 찾고 같은 이름을 가진 다른 어셈블리와 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-106">The runtime uses this information to locate the assembly and differentiate it from other assemblies with the same name.</span></span> <span data-ttu-id="cb7ca-107">예를 들어 `myTypes`라는 강력한 이름의 어셈블리에는 다음과 같은 정규화된 이름이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-107">For example, a strong-named assembly called `myTypes` could have the following fully qualified name:</span></span>  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  <span data-ttu-id="cb7ca-108">.NET Framework 버전 2.0에서는 어셈블리의 프로세서별 버전을 허용하기 위해 프로세서 아키텍처가 어셈블리 ID에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-108">Processor architecture is added to the assembly identity in the .NET Framework version 2.0, to allow processor-specific versions of assemblies.</span></span> <span data-ttu-id="cb7ca-109">프로세서 아키텍처를 통해서만 ID가 다른 어셈블리의 버전을 만들 수 있습니다(예: 32비트 및 64비트 프로세서별 버전).</span><span class="sxs-lookup"><span data-stu-id="cb7ca-109">You can create versions of an assembly whose identity differs only by processor architecture, for example 32-bit and 64-bit processor-specific versions.</span></span> <span data-ttu-id="cb7ca-110">강력한 이름에는 프로세서 아키텍처가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-110">Processor architecture is not required for strong names.</span></span> <span data-ttu-id="cb7ca-111">자세한 내용은 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-111">For more information, see <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="cb7ca-112">이 예제에서 정규화된 이름은 `myTypes` 어셈블리에 공개 키 토큰과 함께 강력한 이름이 있고, 영어(미국)에 대한 문화권 값이 있고, 버전 번호 1.0.1234.0이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-112">In this example, the fully qualified name indicates that the `myTypes` assembly has a strong name with a public key token, has the culture value for US English, and has a version number of 1.0.1234.0.</span></span> <span data-ttu-id="cb7ca-113">해당 프로세서 아키텍처는 "msil"이며, 이는 운영 체제 및 프로세서에 따라 32비트 코드 또는 64비트 코드로 JIT(Just-In-Time) 컴파일될 것임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-113">Its processor architecture is "msil", which means that it will be just-in-time (JIT)-compiled to 32-bit code or 64-bit code depending on the operating system and processor.</span></span>  
  
 <span data-ttu-id="cb7ca-114">어셈블리의 형식을 요청하는 코드에는 정규화된 어셈블리 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-114">Code that requests types in an assembly must use a fully qualified assembly name.</span></span> <span data-ttu-id="cb7ca-115">이것을 정규화된 바인딩이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-115">This is called fully qualified binding.</span></span> <span data-ttu-id="cb7ca-116">.NET Framework에서 어셈블리를 참조할 경우 어셈블리 이름만 지정하는 부분 바인딩은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-116">Partial binding, which specifies only an assembly name, is not permitted when referencing assemblies in the .NET Framework.</span></span>  
  
 <span data-ttu-id="cb7ca-117">.NET Framework를 구성하는 어셈블리에 대한 모든 어셈블리 참조에는 어셈블리의 정규화된 이름이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-117">All assembly references to assemblies that make up the .NET Framework also must contain a fully qualified name of the assembly.</span></span> <span data-ttu-id="cb7ca-118">예를 들어 System.Data를 참조하려면 버전 1.0의 .NET Framework 어셈블리에 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-118">For example, to reference the System.Data .NET Framework assembly for version 1.0 would include:</span></span>  
  
```  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
```  
  
 <span data-ttu-id="cb7ca-119">이 버전은 .NET Framework 버전 1.0과 함께 제공된 모든 .NET Framework 어셈블리의 버전 번호와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-119">Note that the version corresponds to the version number of all .NET Framework assemblies that shipped with .NET Framework version 1.0.</span></span> <span data-ttu-id="cb7ca-120">.NET Framework 어셈블리의 경우 문화권 값은 항상 중립적이고 공개 키는 위 예제에 표시된 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-120">For .NET Framework assemblies, the culture value is always neutral, and the public key is the same as shown in the above example.</span></span>  
  
 <span data-ttu-id="cb7ca-121">예를 들어 구성 파일에 어셈블리 참조를 추가하여 추적 수신기를 설정하기 위해 시스템 .NET Framework 어셈블리의 정규화된 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-121">For example, to add an assembly reference in a configuration file to set up a trace listener, you would include the fully qualified name of the system .NET Framework assembly:</span></span>  
  
```xml  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  <span data-ttu-id="cb7ca-122">런타임은 어셈블리에 바인딩할 때 어셈블리 이름의 대/소문자를 구분하지 않고 처리하지만 어셈블리에서 사용된 대/소문자를 보존합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-122">The runtime treats assembly names as case-insensitive when binding to an assembly, but preserves whatever case is used in an assembly name.</span></span> <span data-ttu-id="cb7ca-123">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]의 여러 도구는 어셈블리 이름의 대/소문자를 구분하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-123">Several tools in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] handle assembly names as case-sensitive.</span></span> <span data-ttu-id="cb7ca-124">최상의 결과를 위해서 대/소문자를 구분한 것처럼 어셈블리 이름을 관리하세요.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-124">For best results, manage assembly names as though they were case-sensitive.</span></span>  
  
## <a name="naming-application-components"></a><span data-ttu-id="cb7ca-125">응용 프로그램 구성 요소 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cb7ca-125">Naming Application Components</span></span>  
 <span data-ttu-id="cb7ca-126">런타임은 어셈블리 ID를 확인할 때 파일 이름을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-126">The runtime does not consider the file name when determining an assembly's identity.</span></span> <span data-ttu-id="cb7ca-127">어셈블리 이름, 버전, 문화권 및 강력한 이름으로 구성된 어셈블리 ID는 런타임에 대해 분명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-127">The assembly identity, which consists of the assembly name, version, culture, and strong name, must be clear to the runtime.</span></span>  
  
 <span data-ttu-id="cb7ca-128">예를 들어 myAssembly.dll 어셈블리를 참조하는 myAssembly.exe 어셈블리가 있는 경우 myAssembly.exe를 실행하면 바인딩이 올바르게 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-128">For example, if you have an assembly called myAssembly.exe that references an assembly called myAssembly.dll, binding occurs correctly if you execute myAssembly.exe.</span></span> <span data-ttu-id="cb7ca-129">하지만 또 다른 응용 프로그램이 <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> 메서드를 사용하여 myAssembly.exe를 실행하면 런타임은 myAssembly.exe가 "myAssembly"에 대한 바인딩을 요청할 때 "myAssembly"가 이미 로드되었다고 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-129">However, if another application executes myAssembly.exe using the method <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType>, the runtime determines that "myAssembly" is already loaded when myAssembly.exe requests binding to "myAssembly."</span></span> <span data-ttu-id="cb7ca-130">이 경우 myAssembly.dll은 로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-130">In this case, myAssembly.dll is never loaded.</span></span> <span data-ttu-id="cb7ca-131">myAssembly.exe에 요청된 형식이 포함되어 있지 않으므로 <xref:System.TypeLoadException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-131">Because myAssembly.exe does not contain the requested type , a <xref:System.TypeLoadException> occurs.</span></span>  
  
 <span data-ttu-id="cb7ca-132">이 문제를 방지하려면 응용 프로그램을 구성하는 어셈블리의 이름을 서로 다르게 지정하거나 같은 이름을 가진 어셈블리를 서로 다른 디렉터리에 포함하세요.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-132">To avoid this problem, make sure the assemblies that make up your application do not have the same assembly name or place assemblies with the same name in different directories.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb7ca-133">강력한 이름의 어셈블리를 전역 어셈블리 캐시에 포함할 경우 어셈블리의 파일 이름은 어셈블리 이름(.exe 또는 .dll 등의 파일 이름 확장명 제외)과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-133">If you put a strong-named assembly in the global assembly cache, the assembly's file name must match the assembly name (not including the file name extension, such as .exe or .dll).</span></span> <span data-ttu-id="cb7ca-134">예를 들어 어셈블리의 파일 이름이 myAssembly.dll이면 어셈블리 이름은 myAssembly여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-134">For example, if the file name of an assembly is myAssembly.dll, the assembly name must be myAssembly.</span></span> <span data-ttu-id="cb7ca-135">루트 응용 프로그램 디렉터리에만 배포된 전용 어셈블리의 이름은 파일 이름과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7ca-135">Private assemblies deployed only in the root application directory can have an assembly name that is different from the file name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7ca-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb7ca-136">See Also</span></span>  
 [<span data-ttu-id="cb7ca-137">방법: 어셈블리의 정규화된 이름 식별</span><span class="sxs-lookup"><span data-stu-id="cb7ca-137">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 [<span data-ttu-id="cb7ca-138">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="cb7ca-138">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="cb7ca-139">강력한 이름의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="cb7ca-139">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)  
 [<span data-ttu-id="cb7ca-140">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="cb7ca-140">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="cb7ca-141">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="cb7ca-141">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="cb7ca-142">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cb7ca-142">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
