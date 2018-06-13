---
title: Fusion 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86cb59c0935c193a9865d5ace5fe11c96226d9e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435906"
---
# <a name="fusion-global-static-functions"></a><span data-ttu-id="6f717-102">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-102">Fusion Global Static Functions</span></span>
<span data-ttu-id="6f717-103">이 여기서는 fusion API를 사용 하는 관리 되지 않는 전역 정적 함수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-103">This section describes the unmanaged global static functions that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f717-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6f717-104">In This Section</span></span>  
 [<span data-ttu-id="6f717-105">ClearDownloadCache 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-105">ClearDownloadCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 <span data-ttu-id="6f717-106">다운로드 된 어셈블리의 전역 어셈블리 캐시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-106">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
 [<span data-ttu-id="6f717-107">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-107">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 <span data-ttu-id="6f717-108">동일한 지 여부를 확인 하려면 두 개의 어셈블리 id를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-108">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
 [<span data-ttu-id="6f717-109">CreateApplicationContext 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-109">CreateApplicationContext Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 <span data-ttu-id="6f717-110">내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-110">Internal only.</span></span> <span data-ttu-id="6f717-111">(이 함수는.NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="6f717-111">(This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="6f717-112">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-112">CreateAssemblyCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 <span data-ttu-id="6f717-113">새에 대 한 포인터를 가져옵니다 [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) 전역 어셈블리 캐시를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-113">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6f717-114">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-114">CreateAssemblyEnum Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 <span data-ttu-id="6f717-115">에 대 한 포인터를 가져옵니다는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 를 나타내는 지정된 된 어셈블리에 존재 하는 개체의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-115">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that represents a list of objects that exist in the specified assembly.</span></span>  
  
 [<span data-ttu-id="6f717-116">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-116">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 <span data-ttu-id="6f717-117">에 대 한 포인터를 가져옵니다는 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 지정한 이름 가진 어셈블리의 고유 id를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-117">Gets a pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
 [<span data-ttu-id="6f717-118">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-118">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 <span data-ttu-id="6f717-119">지정된 된 파일에 대 한 기록 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-119">Creates a history reader for the specified file.</span></span>  
  
 [<span data-ttu-id="6f717-120">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-120">CreateInstallReferenceEnum Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 <span data-ttu-id="6f717-121">에 대 한 포인터를 가져옵니다는 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 목록이 지정된 된 어셈블리에 대 한 응용 프로그램의 한 참조를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-121">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
 [<span data-ttu-id="6f717-122">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-122">GetAppIdAuthority Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 <span data-ttu-id="6f717-123">에 대 한 포인터를 가져옵니다는 [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) 응용 프로그램 id 및 참조에 대 한 키를 관리 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-123">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="6f717-124">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-124">GetAssemblyIdentityFromFile Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 <span data-ttu-id="6f717-125">에 대 한 포인터를 가져옵니다는 `IUnknown` 개체와 지정한 `IID` 지정 된 파일 경로에 있는 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-125">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
 [<span data-ttu-id="6f717-126">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-126">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 <span data-ttu-id="6f717-127">지정된 된 플래그를 사용 하 여 캐시 된 어셈블리에 경로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-127">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
 [<span data-ttu-id="6f717-128">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-128">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 <span data-ttu-id="6f717-129">응용 프로그램 기록 디렉터리의 경로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-129">Retrieves the path of the application history directory.</span></span>  
  
 [<span data-ttu-id="6f717-130">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-130">GetIdentityAuthority Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 <span data-ttu-id="6f717-131">에 대 한 포인터를 가져옵니다는 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) 코드 개체에 대 한 키를 관리 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-131">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
 [<span data-ttu-id="6f717-132">IsFrameworkAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-132">IsFrameworkAssembly Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 <span data-ttu-id="6f717-133">지정된 된 어셈블리 관리 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-133">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
 [<span data-ttu-id="6f717-134">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-134">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 <span data-ttu-id="6f717-135">공용 언어 런타임에서 다운로드 캐시를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-135">Deletes the common language runtime download cache.</span></span>  
  
 [<span data-ttu-id="6f717-136">PreBindAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="6f717-136">PreBindAssemblyEx Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 <span data-ttu-id="6f717-137">어셈블리에 대 한 사후 정책 표시 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f717-137">Gets the post-policy display name for an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f717-138">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6f717-138">Related Sections</span></span>  
 [<span data-ttu-id="6f717-139">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f717-139">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [<span data-ttu-id="6f717-140">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="6f717-140">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="6f717-141">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="6f717-141">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [<span data-ttu-id="6f717-142">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="6f717-142">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
