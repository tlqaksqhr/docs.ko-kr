---
title: ".NET Framework에 COM 구성 요소 노출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9361de4726b1dc58238db5ca7b5605f2cc75485d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="8c1f8-102">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="8c1f8-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="8c1f8-103">이 섹션에서는 프로세스를 기존 COM 구성 요소를 관리 코드에 노출하는 데 필요한 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="8c1f8-104">.NET Framework와 강력하게 통합되는 COM 서버를 작성하는 방법에 대한 자세한 내용은 [상호 운용을 위한 디자인 고려 사항](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).</span></span>  
  
 <span data-ttu-id="8c1f8-105">기존 COM 구성요소는 중간 계층 비즈니스 응용 프로그램 또는 격리된 기능으로서 관리 코드의 중요한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="8c1f8-106">이상적인 구성 요소는 주 interop 어셈블리를 포함하고 COM을 통해 적용되는 프로그래밍 표준을 엄격하게 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="8c1f8-107">.NET Framework에 COM 구성 요소를 노출하려면</span><span class="sxs-lookup"><span data-stu-id="8c1f8-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="8c1f8-108">[형식 라이브러리를 어셈블리로 가져옵니다](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="8c1f8-108">[Import a type library as an assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="8c1f8-109">공용 언어 런타임에는 COM 형식을 비롯한 모든 형식에 대한 메타데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="8c1f8-110">메타데이터로 가져온 COM 형식이 포함된 어셈블리를 가져오는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="8c1f8-111">[관리 코드에서 COM 형식을 만듭니다](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span><span class="sxs-lookup"><span data-stu-id="8c1f8-111">[Create COM types in managed Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
     <span data-ttu-id="8c1f8-112">관리되는 형식의 경우와 같은 방식으로 COM 형식을 검사하고, 인스턴스를 활성화하고, COM 개체에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="8c1f8-113">[Interop 프로젝트를 컴파일합니다](../../../docs/framework/interop/compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="8c1f8-113">[Compile an interop project](../../../docs/framework/interop/compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="8c1f8-114">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# 및 C++를 포함하여 CLS(공용 언어 사양)와 호환되는 여러 가지 언어용 컴파일러를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="8c1f8-115">[Interop 응용 프로그램을 배포합니다](../../../docs/framework/interop/deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="8c1f8-115">[Deploy an interop application](../../../docs/framework/interop/deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="8c1f8-116">Interop 응용 프로그램은 전역 어셈블리 캐시에 [강력한 이름의](../../../docs/framework/app-domains/strong-named-assemblies.md) 서명된 어셈블리로서 가장 잘 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c1f8-116">Interop applications are best deployed as [strong-named](../../../docs/framework/app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c1f8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c1f8-117">See Also</span></span>  
 [<span data-ttu-id="8c1f8-118">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="8c1f8-118">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="8c1f8-119">상호 운용을 위한 디자인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8c1f8-119">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [<span data-ttu-id="8c1f8-120">COM Interop 샘플: .NET 클라이언트 및 COM 서버</span><span class="sxs-lookup"><span data-stu-id="8c1f8-120">COM Interop Sample: .NET Client and COM Server</span></span>](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [<span data-ttu-id="8c1f8-121">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8c1f8-121">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="8c1f8-122">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="8c1f8-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
