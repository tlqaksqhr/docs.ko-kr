---
title: 전역 어셈블리 캐시
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache)
- ACLs [.NET Framework]
- global assembly cache
- cache [.NET Framework], global assembly cache
- global assembly cache, about
- access control lists [.NET Framework]
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3667a644253ab52d8421a1d4222e0bf8c03624c1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751976"
---
# <a name="global-assembly-cache"></a><span data-ttu-id="604b7-102">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="604b7-102">Global Assembly Cache</span></span>
<span data-ttu-id="604b7-103">공용 언어 런타임이 설치된 각 컴퓨터에는 전역 어셈블리 캐시라는 컴퓨터 수준의 코드 캐시가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-103">Each computer where the Common Language Runtime is installed has a machine-wide code cache called the Global Assembly Cache.</span></span> <span data-ttu-id="604b7-104">전역 어셈블리 캐시에는 컴퓨터의 여러 응용 프로그램에서 공유하도록 특별히 지정된 어셈블리가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-104">The Global Assembly Cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span>  
  
 <span data-ttu-id="604b7-105">필요할 경우에만 어셈블리를 전역 어셈블리 캐시에 설치하여 어셈블리를 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-105">You should share assemblies by installing them into the Global Assembly Cache only when you need to.</span></span> <span data-ttu-id="604b7-106">일반적으로 어셈블리 공유가 명시적으로 필요하지 않은 경우에는 어셈블리 종속성은 pirvate으로 유지하고 어셈블리를 응용 프로그램 디렉터리에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-106">As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="604b7-107">또한 어셈블리가 COM interop 또는 비관리 코드에 액세스 가능하게 설정하기 위해 어셈블리를 전역 어셈블리 캐시에 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-107">In addition, it is not necessary to install assemblies into the Global Assembly Cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="604b7-108">어셈블리를 전역 어셈블리 캐시에 명시적으로 설치하지 않으려고 하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-108">There are scenarios where you explicitly do not want to install an assembly into the Global Assembly Cache.</span></span> <span data-ttu-id="604b7-109">응용 프로그램을 구성하는 어셈블리 중 하나를 전역 어셈블리 캐시에 배치하면 **xcopy** 명령을 사용하여 응용 프로그램 디렉터리를 복사하는 방식으로 응용 프로그램을 더 이상 복제하거나 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-109">If you place one of the assemblies that make up an application in the Global Assembly Cache, you can no longer replicate or install the application by using the **xcopy** command to copy the application directory.</span></span> <span data-ttu-id="604b7-110">전역 어셈블리 캐시의 어셈블리도 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-110">You must move the assembly in the Global Assembly Cache as well.</span></span>  
  
 <span data-ttu-id="604b7-111">어셈블리를 전역 어셈블리 캐시에 배포하는 다음 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-111">There are two ways to deploy an assembly into the Global Assembly Cache:</span></span>  
  
-   <span data-ttu-id="604b7-112">전역 어셈블리 캐시와 함께 사용하도록 디자인된 설치 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-112">Use an installer designed to work with the Global Assembly Cache.</span></span> <span data-ttu-id="604b7-113">이것은 어셈블리를 전역 어셈블리 캐시에 설치하기 위한 기본 설정된 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-113">This is the preferred option for installing assemblies into the Global Assembly Cache.</span></span>  
  
-   <span data-ttu-id="604b7-114">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 제공된 [전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)라는 개발자 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-114">Use a developer tool called the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md), provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="604b7-115">배포 시나리오에서는 전역 어셈블리 캐시에 어셈블리를 설치할 때 Windows Installer를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-115">In deployment scenarios, use Windows Installer to install assemblies into the Global Assembly Cache.</span></span> <span data-ttu-id="604b7-116">전역 어셈블리 캐시 도구는 개발 시나리오에서만 사용합니다. 그 이유는 이 도구가 어셈블리 참조 계산 및 Windows Installer를 사용할 때 제공되는 기타 기능을 제공하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-116">Use the Global Assembly Cache tool only in development scenarios, because it does not provide assembly reference counting and other features provided when using the Windows Installer.</span></span>  
  
 <span data-ttu-id="604b7-117">.NET Framework 4부터 전역 어셈블리 캐시의 기본 위치는 **%windir%\Microsoft.NET\assembly**입니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-117">Starting with the .NET Framework 4, the default location for the Global Assembly Cache is **%windir%\Microsoft.NET\assembly**.</span></span> <span data-ttu-id="604b7-118">.NET Framework의 이전 버전에서 기본 위치는 **%windir%\assembly**입니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-118">In earlier versions of the .NET Framework, the default location is **%windir%\assembly**.</span></span>  
  
 <span data-ttu-id="604b7-119">관리자는 대부분 쓰기 및 실행 액세스를 제어하기 위해 ACL(액세스 제어 목록)을 사용하여 systemroot 디렉터리를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-119">Administrators often protect the systemroot directory using an access control list (ACL) to control write and execute access.</span></span> <span data-ttu-id="604b7-120">전역 어셈블리 캐시는 systemroot 디렉터리의 하위 디렉터리에 설치되므로 해당 디렉터리의 ACL을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-120">Because the Global Assembly Cache is installed in a subdirectory of the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="604b7-121">관리자 권한을 가진 사용자만 전역 어셈블리 캐시에서 파일을 삭제하도록 허용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-121">It is recommended that only users with Administrator privileges be allowed to delete files from the Global Assembly Cache.</span></span>  
  
 <span data-ttu-id="604b7-122">전역 어셈블리 캐시에 배포된 어셈블리에 강력한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-122">Assemblies deployed in the Global Assembly Cache must have a strong name.</span></span> <span data-ttu-id="604b7-123">어셈블리가 전역 어셈블리 캐시에 추가되면 어셈블리를 구성하는 모든 파일에 대한 무결성 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-123">When an assembly is added to the Global Assembly Cache, integrity checks are performed on all files that make up the assembly.</span></span> <span data-ttu-id="604b7-124">예를 들어 파일이 변경되었지만 매니페스트가 변경을 반영하지 않는 경우 캐시는 이러한 무결성 검사를 수행하여 어셈블리가 변조되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="604b7-124">The cache performs these integrity checks to ensure that an assembly has not been tampered with, for example, when a file has changed but the manifest does not reflect the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604b7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="604b7-125">See Also</span></span>  
 [<span data-ttu-id="604b7-126">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="604b7-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="604b7-127">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="604b7-127">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="604b7-128">강력한 이름의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="604b7-128">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)
