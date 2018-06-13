---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b7eeadd532e5a53c693cc1cde59150777d7edc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433869"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="32abc-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="32abc-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="32abc-103">제공 된 포인터 목록에 있는 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32abc-104">구문</span><span class="sxs-lookup"><span data-stu-id="32abc-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32abc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32abc-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="32abc-106">[in] 검색할 어셈블리에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="32abc-107">유효한 값은 형식의 `IAssemblyName` 또는 `IReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32abc-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="32abc-108">Return Value</span></span>  
  
|<span data-ttu-id="32abc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32abc-109">HRESULT</span></span>|<span data-ttu-id="32abc-110">설명</span><span class="sxs-lookup"><span data-stu-id="32abc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32abc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="32abc-111">S_OK</span></span>|<span data-ttu-id="32abc-112">문자열의 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="32abc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="32abc-113">S_FALSE</span></span>|<span data-ttu-id="32abc-114">문자열 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="32abc-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32abc-115">E_FAIL</span></span>|<span data-ttu-id="32abc-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32abc-117">메서드가 E_FAIL을 반환 하는 경우 공용 언어 런타임 숨겨지면 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="32abc-118">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32abc-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32abc-119">Requirements</span></span>  
 <span data-ttu-id="32abc-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32abc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32abc-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32abc-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32abc-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="32abc-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32abc-123">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32abc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32abc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32abc-124">See Also</span></span>  
 [<span data-ttu-id="32abc-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32abc-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="32abc-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32abc-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="32abc-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32abc-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="32abc-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32abc-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
