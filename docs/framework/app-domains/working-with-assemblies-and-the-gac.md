---
title: 어셈블리 및 전역 어셈블리 캐시 사용
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e780ed7e841809f21130822babe55ad4935670
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744306"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="5dfe4-102">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="5dfe4-102">Working with Assemblies and the Global Assembly Cache</span></span>
<span data-ttu-id="5dfe4-103">여러 응용 프로그램에서 어셈블리를 공유하려면 어셈블리를 전역 어셈블리 캐시에 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-103">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="5dfe4-104">공용 언어 런타임이 설치된 각 컴퓨터에는 이 컴퓨터 수준의 코드 캐시가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-104">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="5dfe4-105">전역 어셈블리 캐시에는 컴퓨터의 여러 응용 프로그램에서 공유하도록 특별히 지정된 어셈블리가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-105">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="5dfe4-106">전역 어셈블리 캐시에 설치하려면 어셈블리에 강력한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-106">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dfe4-107">전역 어셈블리 캐시에 배치된 어셈블리에는 같은 어셈블리 이름과 파일 이름(파일 이름 확장명 제외)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-107">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="5dfe4-108">예를 들어 어셈블리 이름이 myAssembly인 어셈블리의 파일 이름은 myAssembly.exe 또는 myAssembly.dll이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-108">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
 <span data-ttu-id="5dfe4-109">필요할 경우에만 어셈블리를 전역 어셈블리 캐시에 설치하여 어셈블리를 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-109">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="5dfe4-110">일반적으로 어셈블리 공유가 명시적으로 필요하지 않은 경우에는 어셈블리 종속성은 pirvate으로 유지하고 어셈블리를 응용 프로그램 디렉터리에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-110">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="5dfe4-111">또한 어셈블리가 COM interop 또는 비관리 코드에 액세스 가능하게 설정하기 위해 어셈블리를 전역 어셈블리 캐시에 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-111">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
 <span data-ttu-id="5dfe4-112">어셈블리를 전역 어셈블리 캐시에 설치해야 하는 몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-112">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="5dfe4-113">공유된 위치.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-113">Shared location.</span></span>  
  
     <span data-ttu-id="5dfe4-114">응용 프로그램에서 사용해야 하는 어셈블리는 전역 어셈블리 캐시에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-114">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="5dfe4-115">예를 들어 모든 응용 프로그램에서 전역 어셈블리 캐시에 있는 어셈블리를 사용해야 하는 경우 버전 정책 설명을 Machine.config 파일에 추가하여 참조를 어셈블리로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-115">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
-   <span data-ttu-id="5dfe4-116">파일 보안.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-116">File security.</span></span>  
  
     <span data-ttu-id="5dfe4-117">관리자는 대부분 쓰기 및 실행 액세스를 제어하기 위해 ACL(액세스 제어 목록)을 사용하여 systemroot 디렉터리를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-117">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="5dfe4-118">전역 어셈블리 캐시는 systemroot 디렉터리에 설치되므로 해당 디렉터리의 ACL을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-118">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="5dfe4-119">관리자 권한을 가진 사용자만 전역 어셈블리 캐시에서 파일을 삭제하도록 허용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-119">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
-   <span data-ttu-id="5dfe4-120">Side-by-side 버전 관리.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-120">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="5dfe4-121">이름이 같지만 버전 정보가 서로 다른 여러 어셈블리 복사본을 전역 어셈블리 캐시에서 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-121">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="5dfe4-122">추가 검색 위치.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-122">Additional search location.</span></span>  
  
     <span data-ttu-id="5dfe4-123">공용 언어 런타임은 구성 파일에서 코드베이스 정보를 검색 또는 사용하기 전에 어셈블리 요청과 일치하는 어셈블리가 전역 어셈블리 캐시에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-123">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="5dfe4-124">어셈블리를 전역 어셈블리 캐시에 명시적으로 설치하지 않으려고 하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-124">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="5dfe4-125">응용 프로그램을 구성하는 어셈블리 중 하나를 전역 어셈블리 캐시에 배치하면 XCOPY를 사용하여 응용 프로그램 디렉터리를 복사하는 방식으로 응용 프로그램을 더 이상 복제하거나 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-125">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="5dfe4-126">이 경우 어셈블리를 전역 어셈블리 캐시로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-126">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dfe4-127">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5dfe4-127">In This Section</span></span>  
 [<span data-ttu-id="5dfe4-128">방법: 전역 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="5dfe4-128">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 <span data-ttu-id="5dfe4-129">어셈블리를 전역 어셈블리 캐시에 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-129">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5dfe4-130">방법: 전역 어셈블리 캐시의 내용 보기</span><span class="sxs-lookup"><span data-stu-id="5dfe4-130">How to: View the Contents of the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 <span data-ttu-id="5dfe4-131">[Gacutil.exe(전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하여 전역 어셈블리 캐시의 콘텐츠를 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-131">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5dfe4-132">방법: 전역 어셈블리 캐시에서 어셈블리 제거</span><span class="sxs-lookup"><span data-stu-id="5dfe4-132">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 <span data-ttu-id="5dfe4-133">[Gacutil.exe(전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하여 전역 어셈블리 캐시에서 어셈블리를 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5dfe4-134">전역 어셈블리 캐시에서 서비스되는 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="5dfe4-134">Using Serviced Components with the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 <span data-ttu-id="5dfe4-135">서비스되는 구성 요소(관리되는 COM+ 구성 요소)를 전역 어셈블리 캐시에 배치하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-135">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5dfe4-136">관련 단원</span><span class="sxs-lookup"><span data-stu-id="5dfe4-136">Related Sections</span></span>  
 [<span data-ttu-id="5dfe4-137">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="5dfe4-137">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="5dfe4-138">어셈블리 만들기에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-138">Provides an overview of creating assemblies.</span></span>  
  
 [<span data-ttu-id="5dfe4-139">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="5dfe4-139">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 <span data-ttu-id="5dfe4-140">전역 어셈블리 캐시를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-140">Describes the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5dfe4-141">방법: 어셈블리 내용 보기</span><span class="sxs-lookup"><span data-stu-id="5dfe4-141">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="5dfe4-142">[Ildasm.exe(IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리의 MSIL(Microsoft Intermediate Language) 정보를 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-142">Explains how to use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
 [<span data-ttu-id="5dfe4-143">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5dfe4-143">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="5dfe4-144">공용 언어 런타임이 응용 프로그램을 구성하는 어셈블리를 찾고 로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-144">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
 [<span data-ttu-id="5dfe4-145">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5dfe4-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="5dfe4-146">관리되는 응용 프로그램의 빌드 블록인 어셈블리를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfe4-146">Describes assemblies, the building blocks of managed applications.</span></span>
