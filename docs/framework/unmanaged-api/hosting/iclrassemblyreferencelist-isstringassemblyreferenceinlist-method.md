---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad7230731775cbc56dd0f1eaed72df19512d3733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432598"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="10544-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="10544-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="10544-103">제공 된 이름이 목록에 있는 어셈블리의 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10544-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10544-104">구문</span><span class="sxs-lookup"><span data-stu-id="10544-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10544-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10544-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="10544-106">[in] 검색 하려는 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10544-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10544-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="10544-107">Return Value</span></span>  
  
|<span data-ttu-id="10544-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10544-108">HRESULT</span></span>|<span data-ttu-id="10544-109">설명</span><span class="sxs-lookup"><span data-stu-id="10544-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10544-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="10544-110">S_OK</span></span>|<span data-ttu-id="10544-111">문자열의 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="10544-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="10544-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="10544-112">S_FALSE</span></span>|<span data-ttu-id="10544-113">문자열 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10544-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="10544-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10544-114">E_FAIL</span></span>|<span data-ttu-id="10544-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="10544-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10544-116">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 숨겨지면 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="10544-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="10544-117">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="10544-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10544-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10544-118">Requirements</span></span>  
 <span data-ttu-id="10544-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10544-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10544-120">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10544-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10544-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="10544-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10544-122">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10544-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10544-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10544-123">See Also</span></span>  
 [<span data-ttu-id="10544-124">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10544-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="10544-125">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10544-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="10544-126">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10544-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="10544-127">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10544-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
