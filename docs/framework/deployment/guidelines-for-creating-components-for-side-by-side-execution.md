---
title: Side-by-Side 실행용 구성 요소를 만들기 위한 지침
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, multiple application versions
- side-by-side execution, multiple component versions
ms.assetid: 5c540161-6e40-42e9-be92-6175aee2c46a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f45e68d9d340d857bc25b3848bd687e46fd73c52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391035"
---
# <a name="guidelines-for-creating-components-for-side-by-side-execution"></a><span data-ttu-id="d532e-102">Side-by-Side 실행용 구성 요소를 만들기 위한 지침</span><span class="sxs-lookup"><span data-stu-id="d532e-102">Guidelines for Creating Components for Side-by-Side Execution</span></span>
<span data-ttu-id="d532e-103">다음 일반 지침에 따라 Side-by-Side 실행용으로 디자인된 관리되는 응용 프로그램 또는 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-103">Follow these general guidelines to create managed applications or components designed for side-by-side execution:</span></span>  
  
-   <span data-ttu-id="d532e-104">파일의 특정 버전에 형식 ID를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-104">Bind type identity to a particular version of a file.</span></span>  
  
     <span data-ttu-id="d532e-105">공용 언어 런타임은 강력한 이름의 어셈블리를 사용하여 특정 파일 버전에 형식 ID를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-105">The common language runtime binds type identity to a particular file version by using strong-named assemblies.</span></span> <span data-ttu-id="d532e-106">Side-by-side 실행용 응용 프로그램 또는 구성 요소를 만들려면 모든 어셈블리에 강력한 이름을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-106">To create an application or component for side-by-side execution, you must give all assemblies a strong name.</span></span> <span data-ttu-id="d532e-107">이를 통해 정확한 형식 ID를 만들고 형식 확인이 올바른 파일로 전달되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-107">This creates precise type identity and ensures that any type resolution is directed to the correct file.</span></span> <span data-ttu-id="d532e-108">강력한 이름의 어셈블리에는 런타임이 바인딩 요청을 충족하는 올바른 파일을 찾는 데 사용하는 버전, 문화권 및 게시자 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-108">A strong-named assembly contains version, culture, and publisher information that the runtime uses to locate the correct file to fulfill a binding request.</span></span>  
  
-   <span data-ttu-id="d532e-109">버전 인식 저장소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-109">Use version-aware storage.</span></span>  
  
     <span data-ttu-id="d532e-110">런타임은 전역 어셈블리 캐시를 사용하여 버전 인식 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-110">The runtime uses the global assembly cache to provide version-aware storage.</span></span> <span data-ttu-id="d532e-111">전역 어셈블리 캐시는 .NET Framework를 사용하는 모든 컴퓨터에 설치된 버전 인식 디렉터리 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-111">The global assembly cache is a version-aware directory structure installed on every computer that uses the .NET Framework.</span></span> <span data-ttu-id="d532e-112">전역 어셈블리 캐시에 설치된 어셈블리는 해당 어셈블리의 새 버전을 설치할 경우 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-112">Assemblies installed in the global assembly cache are not overwritten when a new version of that assembly is installed.</span></span>  
  
-   <span data-ttu-id="d532e-113">격리 상태로 실행되는 응용 프로그램 또는 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-113">Create an application or component that runs in isolation.</span></span>  
  
     <span data-ttu-id="d532e-114">격리 상태로 실행되는 응용 프로그램 또는 구성 요소는 응용 프로그램이나 구성 요소의 두 인스턴스가 동시에 실행될 때 충돌을 방지하려면 리소스를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-114">An application or component that runs in isolation must manage resources to avoid conflicts when two instances of the application or component are running simultaneously.</span></span> <span data-ttu-id="d532e-115">또한 응용 프로그램 또는 구성 요소는 버전별 파일 구조를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-115">The application or component must also use a version-specific file structure.</span></span>  
  
## <a name="application-and-component-isolation"></a><span data-ttu-id="d532e-116">응용 프로그램 및 구성 요소 격리</span><span class="sxs-lookup"><span data-stu-id="d532e-116">Application and Component Isolation</span></span>  
 <span data-ttu-id="d532e-117">Side-by-side 실행용 응용 프로그램 또는 구성 요소를 성공적으로 디자인하는 한 가지 핵심 요소는 격리입니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-117">One key to successfully designing an application or component for side-by-side execution is isolation.</span></span> <span data-ttu-id="d532e-118">응용 프로그램 또는 구성 요소는 특히 파일 I/O를 비롯하여 모든 리소스를 격리된 방식으로 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-118">The application or component must manage all resources, particularly file I/O, in an isolated manner.</span></span> <span data-ttu-id="d532e-119">다음 지침에 따라 응용 프로그램 또는 구성 요소가 격리 상태로 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-119">Follow these guidelines to make sure your application or component runs in isolation:</span></span>  
  
-   <span data-ttu-id="d532e-120">버전별 방식으로 레지스트리에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-120">Write to the registry in a version-specific way.</span></span> <span data-ttu-id="d532e-121">버전을 나타내는 값을 Hive 또는 키에 저장하고 구성 요소 버전 간에 정보나 상태를 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-121">Store values in hives or keys that indicate the version, and do not share information or state across versions of a component.</span></span> <span data-ttu-id="d532e-122">이렇게 하면 동시에 실행되는 응용 프로그램 또는 구성 요소 두 개가 정보를 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-122">This prevents two applications or components running at the same time from overwriting information.</span></span>  
  
-   <span data-ttu-id="d532e-123">경합 상태가 발생하지 않도록 명명된 커널 개체를 버전별로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-123">Make named kernel objects version-specific so that a race condition does not occur.</span></span> <span data-ttu-id="d532e-124">예를 들어 경합 상태는 같은 응용 프로그램의 두 가지 버전의 두 세마포가 서로 대기하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-124">For example, a race condition occurs when two semaphores from two versions of the same application wait on each other.</span></span>  
  
-   <span data-ttu-id="d532e-125">파일 및 디렉터리 이름을 버전 인식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-125">Make file and directory names version-aware.</span></span> <span data-ttu-id="d532e-126">이는 파일 구조에서 버전 정보를 사용해야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-126">This means that file structures should rely on version information.</span></span>  
  
-   <span data-ttu-id="d532e-127">사용자 계정 및 그룹을 버전별 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-127">Create user accounts and groups in a version-specific manner.</span></span> <span data-ttu-id="d532e-128">응용 프로그램에서 만들어진 사용자 계정 및 그룹은 버전으로 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-128">User accounts and groups created by an application should be identified by version.</span></span> <span data-ttu-id="d532e-129">응용 프로그램 버전 간에 사용자 계정 및 그룹을 공유하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-129">Do not share user accounts and groups between versions of an application.</span></span>  
  
## <a name="installing-and-uninstalling-versions"></a><span data-ttu-id="d532e-130">버전 설치 및 제거</span><span class="sxs-lookup"><span data-stu-id="d532e-130">Installing and Uninstalling Versions</span></span>  
 <span data-ttu-id="d532e-131">Side-by-Side 실행용 응용 프로그램을 디자인할 때 버전 설치 및 제거와 관련된 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-131">When designing an application for side-by-side execution, follow these guidelines concerning installing and uninstalling versions:</span></span>  
  
-   <span data-ttu-id="d532e-132">다른 버전의.NET Framework에서 실행 중인 다른 응용 프로그램에서 필요할 수 있는 레지스트리에서 정보를 삭제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-132">Do not delete information from the registry that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="d532e-133">다른 버전의.NET Framework에서 실행 중인 다른 응용 프로그램에서 필요할 수 있는 레지스트리에서 정보를 바꾸지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-133">Do not replace information in the registry that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="d532e-134">다른 버전의.NET Framework에서 실행 중인 다른 응용 프로그램에서 필요할 수 있는 COM 구성 요소를 등록 해제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-134">Do not unregister COM components that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="d532e-135">이미 등록된 COM 서버에 대한 **InprocServer32** 또는 기타 레지스트리 항목을 변경하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-135">Do not change **InprocServer32** or other registry entries for a COM server that was already registered.</span></span>  
  
-   <span data-ttu-id="d532e-136">다른 버전의.NET Framework에서 실행 중인 다른 응용 프로그램에서 필요할 수 있는 사용자 계정 또는 그룹을 삭제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-136">Do not delete user accounts or groups that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="d532e-137">버전이 지정되지 않은 경로를 포함하는 아무것도 레지스트리에 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d532e-137">Do not add anything to the registry that contains an unversioned path.</span></span>  
  
## <a name="file-version-number-and-assembly-version-number"></a><span data-ttu-id="d532e-138">파일 버전 번호 및 어셈블리 버전 번호</span><span class="sxs-lookup"><span data-stu-id="d532e-138">File Version Number and Assembly Version Number</span></span>  
 <span data-ttu-id="d532e-139">파일 버전은 런타임에서 사용되지 않는 Win32 버전 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-139">File version is a Win32 version resource that is not used by the runtime.</span></span> <span data-ttu-id="d532e-140">일반적으로, 내부 업데이트에 대해서도 파일 버전을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-140">In general, you update the file version even for an in-place update.</span></span> <span data-ttu-id="d532e-141">두 동일한 파일에 서로 다른 파일 버전 정보를 포함될 수 있고 서로 다른 두 파일에 같은 파일 버전 정보를 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-141">Two identical files can have different file version information, and two different files can have the same file version information.</span></span>  
  
 <span data-ttu-id="d532e-142">어셈블리 버전은 런타임에서 어셈블리 바인딩에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-142">The assembly version is used by the runtime for assembly binding.</span></span> <span data-ttu-id="d532e-143">버전 번호가 다른 두 동일한 어셈블리는 런타임에서 서로 다른 두 어셈블리로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-143">Two identical assemblies with different version numbers are treated as two different assemblies by the runtime.</span></span>  
  
 <span data-ttu-id="d532e-144">[전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하여 파일 버전 번호만 최신일 경우 어셈블리를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-144">The [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) allows you to replace an assembly when only the file version number is newer.</span></span> <span data-ttu-id="d532e-145">일반적으로 설치 관리자는 어셈블리 버전 번호가 더 클 경우가 아니면 어셈블리를 통해 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d532e-145">The installer generally does not install over an assembly unless the assembly version number is greater.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d532e-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d532e-146">See Also</span></span>  
 [<span data-ttu-id="d532e-147">Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="d532e-147">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)  
 [<span data-ttu-id="d532e-148">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="d532e-148">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
