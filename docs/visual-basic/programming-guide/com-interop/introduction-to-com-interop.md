---
title: "COM Interop (Visual Basic) 소개 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interop assemblies
- COM interop, about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6a50a89db3f24d7e34c1fc683b5f712f3a6992bf
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-com-interop-visual-basic"></a><span data-ttu-id="4b722-102">COM Interop 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b722-102">Introduction to COM Interop (Visual Basic)</span></span>
<span data-ttu-id="4b722-103">구성 요소 개체 모델 (COM)에 다른 구성 요소를 응용 프로그램을 호스트 하는 기능을 노출 하는 개체 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-103">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="4b722-104">COM 개체 Windows 오랜 기간 동안 프로그래밍 기초 였을 하는 동안 공용 언어 런타임 (CLR)에 대 한 설계 된 응용 프로그램에는 다양 한 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-104">While COM objects have been fundamental to Windows programming for many years, applications designed for the common language runtime (CLR) offer many advantages.</span></span>  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]<span data-ttu-id="4b722-105">응용 프로그램 대체 com 개발 된</span><span class="sxs-lookup"><span data-stu-id="4b722-105"> applications will eventually replace those developed with COM.</span></span> <span data-ttu-id="4b722-106">그때 까지는 사용 하 여 COM 개체를 만들거나 사용 해야 할 수 있습니다 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-106">Until then, you may have to use or create COM objects by using [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span></span> <span data-ttu-id="4b722-107">COM 상호 운용성 또는 *COM interop*,으로 전환 하면서 기존 COM 개체를 사용할 수 있도록는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 자신의 진도에 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-107">Interoperability with COM, or *COM interop*, enables you to use existing COM objects while transitioning to the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] at your own pace.</span></span>  
  
 <span data-ttu-id="4b722-108">사용 하 여는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] COM 구성 요소를 만들려면 등록이 필요 없는 COM interop을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-108">By using the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] to create COM components, you can use registration-free COM interop.</span></span> <span data-ttu-id="4b722-109">이 DLL 버전은 둘 이상의 버전이 컴퓨터에 설치 되어 있고 최종 사용자는 XCOPY 또는 FTP 사용 응용 프로그램을 컴퓨터에 적절 한 디렉터리를 복사 하려면 실행 될 수 있습니다 경우 사용할 수를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-109">This lets you control which DLL version is enabled when more than one version is installed on a computer, and lets end users use XCOPY or FTP to copy your application to an appropriate directory on their computer where it can be run.</span></span> <span data-ttu-id="4b722-110">자세한 내용은 참조 [등록이 필요 없는 COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-110">For more information, see [Registration-Free COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).</span></span>  
  
## <a name="managed-code-and-data"></a><span data-ttu-id="4b722-111">관리 코드 및 데이터</span><span class="sxs-lookup"><span data-stu-id="4b722-111">Managed Code and Data</span></span>  
 <span data-ttu-id="4b722-112">에 대 한 개발 된 코드는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 라고 *관리 코드*, CLR에서 사용 되는 메타 데이터를 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-112">Code developed for the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is referred to as *managed code*, and contains metadata that is used by CLR.</span></span> <span data-ttu-id="4b722-113">사용 되는 데이터 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램 이라고 *데이터를 관리 되는* 런타임에서 할당 및 메모리를 회수 하 고 수행 형식 검사와 같은 데이터 관련 작업을 관리 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-113">Data used by [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] applications is called *managed data* because the runtime manages data-related tasks such as allocating and reclaiming memory and performing type checking.</span></span> <span data-ttu-id="4b722-114">기본적으로 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] 사용 하 여 관리 코드와 데이터를 되지만 비관리 코드와 interop 어셈블리 (이 페이지에 나중에 설명 됨)를 사용 하 여 COM 개체의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-114">By default, [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] uses managed code and data, but you can access the unmanaged code and data of COM objects using interop assemblies (described later on this page).</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="4b722-115">어셈블리</span><span class="sxs-lookup"><span data-stu-id="4b722-115">Assemblies</span></span>  
 <span data-ttu-id="4b722-116">어셈블리는 기본 빌딩 블록으로는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-116">An assembly is the primary building block of a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span> <span data-ttu-id="4b722-117">기본 제공 하 고 버전 관리 하나 이상의 파일이 포함 된 단일 구현 단위로 배포 되는 기능 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-117">It is a collection of functionality that is built, versioned, and deployed as a single implementation unit containing one or more files.</span></span> <span data-ttu-id="4b722-118">각 어셈블리는 어셈블리 매니페스트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-118">Each assembly contains an assembly manifest.</span></span>  
  
## <a name="type-libraries-and-assembly-manifests"></a><span data-ttu-id="4b722-119">형식 라이브러리와 어셈블리 매니페스트</span><span class="sxs-lookup"><span data-stu-id="4b722-119">Type Libraries and Assembly Manifests</span></span>  
 <span data-ttu-id="4b722-120">형식 라이브러리, 멤버 이름 및 데이터 형식과 같은 COM 개체의 특성에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-120">Type libraries describe characteristics of COM objects, such as member names and data types.</span></span> <span data-ttu-id="4b722-121">에 대 한 동일한 기능을 수행 하는 어셈블리 매니페스트 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-121">Assembly manifests perform the same function for [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] applications.</span></span> <span data-ttu-id="4b722-122">다음에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-122">They include information about the following:</span></span>  
  
-   <span data-ttu-id="4b722-123">어셈블리 id, 버전, 문화권 및 디지털 서명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-123">Assembly identity, version, culture, and digital signature.</span></span>  
  
-   <span data-ttu-id="4b722-124">어셈블리 구현을 구성 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-124">Files that make up the assembly implementation.</span></span>  
  
-   <span data-ttu-id="4b722-125">어셈블리를 구성 하는 리소스 및 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-125">Types and resources that make up the assembly.</span></span> <span data-ttu-id="4b722-126">이 여기에서 내보낸 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-126">This includes those that are exported from it.</span></span>  
  
-   <span data-ttu-id="4b722-127">다른 어셈블리에 대 한 컴파일 시간 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-127">Compile-time dependencies on other assemblies.</span></span>  
  
-   <span data-ttu-id="4b722-128">어셈블리가 제대로 실행 하는 데 필요한 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-128">Permissions required for the assembly to run correctly.</span></span>  
  
 <span data-ttu-id="4b722-129">어셈블리 및 어셈블리 매니페스트 하는 방법에 대 한 자세한 내용은 참조 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-129">For more information about assemblies and assembly manifests, see [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
### <a name="importing-and-exporting-type-libraries"></a><span data-ttu-id="4b722-130">가져오기 및 형식 라이브러리 내보내기</span><span class="sxs-lookup"><span data-stu-id="4b722-130">Importing and Exporting Type Libraries</span></span>  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="4b722-131">Tlbimp으로 형식 라이브러리에서 정보를 가져올 수 있는 유틸리티를 포함 한 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-131"> contains a utility, Tlbimp, that lets you import information from a type library into a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span> <span data-ttu-id="4b722-132">Tlbexp 유틸리티를 사용 하 여 어셈블리에서 형식 라이브러리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-132">You can generate type libraries from assemblies by using the Tlbexp utility.</span></span>  
  
 <span data-ttu-id="4b722-133">Tlbimp와 Tlbexp 하는 방법에 대 한 정보를 참조 하십시오. [Tlbimp.exe (형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) 및 [Tlbexp.exe (형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-133">For information about Tlbimp and Tlbexp, see [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) and [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="4b722-134">Interop 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4b722-134">Interop Assemblies</span></span>  
 <span data-ttu-id="4b722-135">Interop 어셈블리는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리를 브리지 간에 관리 코드와 비관리 코드, COM 개체 멤버에 해당 하는 매핑 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 구성원을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-135">Interop assemblies are [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies that bridge between managed and unmanaged code, mapping COM object members to equivalent [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] managed members.</span></span> <span data-ttu-id="4b722-136">Interop 어셈블리에서 만든 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] 다양 한 상호 운용성 마샬링과 같이 COM 개체, 관련 작업의 세부 정보를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-136">Interop assemblies created by [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] handle many of the details of working with COM objects, such as interoperability marshaling.</span></span>  
  
## <a name="interoperability-marshaling"></a><span data-ttu-id="4b722-137">상호 운용성 마샬링</span><span class="sxs-lookup"><span data-stu-id="4b722-137">Interoperability Marshaling</span></span>  
 <span data-ttu-id="4b722-138">모든 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 응용 프로그램에 사용 되는 프로그래밍 언어에 관계 없이 개체의 상호 운용성을 사용 하도록 설정 하는 공통 형식 집합을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-138">All [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] applications share a set of common types that enable interoperability of objects, regardless of the programming language that is used.</span></span> <span data-ttu-id="4b722-139">매개 변수 및 COM 개체의 반환 값의 경우 관리 코드에서 사용 되는 데이터 형식을 사용 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-139">The parameters and return values of COM objects sometimes use data types that differ from those used in managed code.</span></span> <span data-ttu-id="4b722-140">*상호 운용성 마샬링* 는 COM 개체에서 이동 하는 동안 매개 변수 및 반환 값을 해당 하는 데이터 형식으로는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-140">*Interoperability marshaling* is the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="4b722-141">자세한 내용은 참조 [Interop 마샬링](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b722-141">For more information, see [Interop Marshaling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b722-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b722-142">See Also</span></span>  
 <span data-ttu-id="4b722-143">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b722-143">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="4b722-144"> [연습: COM 개체를 사용한 상속 구현](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="4b722-144"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="4b722-145"> [비관리 코드와의 상호 운용](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="4b722-145"> [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
<span data-ttu-id="4b722-146"> [상호 운용성 문제 해결](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span><span class="sxs-lookup"><span data-stu-id="4b722-146"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span></span>  
<span data-ttu-id="4b722-147"> [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b722-147"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="4b722-148"> [Tlbimp.exe (형식 라이브러리 가져오기)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span><span class="sxs-lookup"><span data-stu-id="4b722-148"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span></span>  
<span data-ttu-id="4b722-149"> [Tlbexp.exe (형식 라이브러리 내보내기)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span><span class="sxs-lookup"><span data-stu-id="4b722-149"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span></span>  
<span data-ttu-id="4b722-150"> [Interop 마샬링](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a) </span><span class="sxs-lookup"><span data-stu-id="4b722-150"> [Interop Marshaling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a) </span></span>  
<span data-ttu-id="4b722-151"> [등록이 필요 없는 COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)</span><span class="sxs-lookup"><span data-stu-id="4b722-151"> [Registration-Free COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)</span></span>
