---
title: "비관리 코드와의 상호 운용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f475877bcb7a794d1a58ef9202735e016363678b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="8ed79-102">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="8ed79-102">Interoperating with Unmanaged Code</span></span>
<span data-ttu-id="8ed79-103">.NET Framework를 기반으로 COM 구성 요소, COM+ 서비스, 외부 형식 라이브러리 및 여러 가지 운영 체제 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-103">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="8ed79-104">관리 개체 모델과 관리되지 않는 개체 모델 간에는 데이터 형식, 메서드 시그니처 및 오류 처리 메커니즘이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-104">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="8ed79-105">.NET Framework 구성 요소와 비관리 코드 간에 상호 운용을 간소화하고 마이그레이션 경로를 줄이기 위해 공용 언어 런타임은 클라이언트 및 서버에서 둘 다 이러한 개체 모델의 차이점을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-105">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>  
  
 <span data-ttu-id="8ed79-106">런타임 제어를 기반으로 실행되는 코드를 관리 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-106">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="8ed79-107">이와 달리 런타임 외부에서 실행되는 코드를 비관리 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-107">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="8ed79-108">비관리 코드로는 COM 구성 요소, ActiveX 인터페이스, Win32 API 함수 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-108">COM components, ActiveX interfaces, and Win32 API functions are examples of unmanaged code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ed79-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8ed79-109">In This Section</span></span>  
 [<span data-ttu-id="8ed79-110">비관리 코드와의 상호 운용 방법 항목</span><span class="sxs-lookup"><span data-stu-id="8ed79-110">Interoperating with Unmanaged Code How-to Topics</span></span>](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 <span data-ttu-id="8ed79-111">비관리 코드와의 상호 운영에 대한 개념 설명서에 나오는 모든 방법 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-111">Provides links to all How-to topics found in the conceptual documentation for interoperating with unmanaged code.</span></span>  
  
 [<span data-ttu-id="8ed79-112">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="8ed79-112">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="8ed79-113">.NET Framework 응용 프로그램에서 COM 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-113">Describes how to use COM components from .NET Framework applications.</span></span>  
  
 [<span data-ttu-id="8ed79-114">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="8ed79-114">Exposing .NET Framework Components to COM</span></span>](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="8ed79-115">COM 응용 프로그램에서 .NET Framework 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-115">Describes how to use .NET Framework components from COM applications.</span></span>  
  
 [<span data-ttu-id="8ed79-116">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="8ed79-116">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="8ed79-117">플랫폼 호출을 사용하여 관리되지 않는 DLL 함수를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="8ed79-118">상호 운용을 위한 디자인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8ed79-118">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 <span data-ttu-id="8ed79-119">통합된 COM 구성 요소를 작성하기 위한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-119">Provides tips for writing integrated COM components.</span></span>  
  
 [<span data-ttu-id="8ed79-120">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="8ed79-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 <span data-ttu-id="8ed79-121">COM interop 및 플랫폼 호출에 대한 마샬링을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-121">Describes marshaling for COM interop and platform invoke.</span></span>  
  
 [<span data-ttu-id="8ed79-122">방법: HRESULT 및 예외 매핑</span><span class="sxs-lookup"><span data-stu-id="8ed79-122">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 <span data-ttu-id="8ed79-123">실행과 HRESULT 간 매핑을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-123">Describes the mapping between exceptions and HRESULTs.</span></span>  
  
 [<span data-ttu-id="8ed79-124">제네릭 형식을 통한 상호 운용</span><span class="sxs-lookup"><span data-stu-id="8ed79-124">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 <span data-ttu-id="8ed79-125">COM interop에서 사용될 경우 제네릭 형식의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-125">Describes the behavior of generic types when used in COM interop.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8ed79-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8ed79-126">Related Sections</span></span>  
 [<span data-ttu-id="8ed79-127">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="8ed79-127">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 <span data-ttu-id="8ed79-128">COM 구성 요소를 .NET Framework 응용 프로그램으로 통합하는 방법에 대한 추가정보 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed79-128">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>
