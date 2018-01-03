---
title: ".NET Framework 응용 프로그램의 COM 상호 운용성(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c84143e22f33f572447c50e33559a52469b181a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="5c8a2-102">.NET Framework 응용 프로그램의 COM 상호 운용성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c8a2-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>
<span data-ttu-id="5c8a2-103">동일한 응용 프로그램에서 COM 개체와.NET Framework 개체를 사용 하려는 경우 개체가 메모리에 존재 하는 방식에서 차이 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="5c8a2-104">관리 되는 메모리에 있는.NET Framework 개체-공용 언어 런타임에 의해 제어 하는 메모리-필요에 따라 런타임에 의해 이동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="5c8a2-105">COM 개체는 관리 되지 않는 메모리에 있으며 다른 메모리 위치로 이동 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="5c8a2-106">및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 이러한 상호 작용을 제어 하는 도구를 관리 및 구성 요소 관리 되지 않는 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-106"> and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="5c8a2-107">관리 코드에 대 한 자세한 내용은 참조 [공용 언어 런타임](../../../standard/clr.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>  
  
 <span data-ttu-id="5c8a2-108">.NET 응용 프로그램에서 COM 개체를 사용 하는 것 외에도 수 또한 사용 하려는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] COM. 통해 관리 되지 않는 코드에서 액세스할 수 있는 개체를 개발 하려면</span><span class="sxs-lookup"><span data-stu-id="5c8a2-108">In addition to using COM objects in .NET applications, you may also want to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to develop objects accessible from unmanaged code through COM.</span></span>  
  
 <span data-ttu-id="5c8a2-109">이 페이지의 링크 COM 및.NET Framework 개체 간의 상호 작용에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c8a2-110">관련 단원</span><span class="sxs-lookup"><span data-stu-id="5c8a2-110">Related Sections</span></span>  
 [<span data-ttu-id="5c8a2-111">COM Interop</span><span class="sxs-lookup"><span data-stu-id="5c8a2-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 <span data-ttu-id="5c8a2-112">Visual basic에서 COM 개체, ActiveX 컨트롤, Win32 Dll, 관리 되는 개체 및 COM 개체의 상속을 포함 하 여 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span>  
  
 [<span data-ttu-id="5c8a2-113">COM Interop 래퍼 오류</span><span class="sxs-lookup"><span data-stu-id="5c8a2-113">COM Interop Wrapper Error</span></span>](/cpp/misc/com-interop-wrapper-error)  
 <span data-ttu-id="5c8a2-114">프로젝트 시스템에서 특정 구성 요소에 대 한 COM 상호 운용성 래퍼를 만들 수 없는 경우 결과 및 옵션에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-114">Describes the consequences and options if the project system cannot create a COM interoperability wrapper for a particular component.</span></span>  
  
 [<span data-ttu-id="5c8a2-115">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="5c8a2-115">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="5c8a2-116">간략하게 관리 코드와 관리 되지 않는 코드 상호 작용 문제 중 일부를 설명 하 고 추가 정보에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-116">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span>  
  
 [<span data-ttu-id="5c8a2-117">COM 래퍼</span><span class="sxs-lookup"><span data-stu-id="5c8a2-117">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md)  
 <span data-ttu-id="5c8a2-118">COM 메서드를 호출 하는 관리 되는 코드를 허용 하는 런타임 호출 가능 래퍼 COM 호출 가능 래퍼는 COM 클라이언트를.NET 개체 메서드를 호출할 수 있는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-118">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span>  
  
 [<span data-ttu-id="5c8a2-119">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="5c8a2-119">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="5c8a2-120">래퍼, 예외, 상속, 스레딩, 이벤트, 변환 및 마샬링 관련 COM 상호 운용성을 다루는 항목에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-120">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span>  
  
 [<span data-ttu-id="5c8a2-121">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="5c8a2-121">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="5c8a2-122">COM 형식 라이브러리에 있는 형식 정의 공용 언어 런타임 어셈블리의 동등한 정의로 변환 하는 데 사용할 수 도구에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c8a2-122">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span>
