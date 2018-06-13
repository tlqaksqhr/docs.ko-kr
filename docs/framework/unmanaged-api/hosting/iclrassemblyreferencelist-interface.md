---
title: ICLRAssemblyReferenceList 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 388b26a5559435ea57300751987d14bc5cb9d50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435299"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="eafdd-102">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eafdd-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="eafdd-103">호스트 아니라 공용 언어 런타임 (CLR)에서 로드 하는 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdd-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eafdd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="eafdd-104">Methods</span></span>  
  
|<span data-ttu-id="eafdd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="eafdd-105">Method</span></span>|<span data-ttu-id="eafdd-106">설명</span><span class="sxs-lookup"><span data-stu-id="eafdd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eafdd-107">IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="eafdd-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="eafdd-108">제공 된 포인터 목록에 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eafdd-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="eafdd-109">IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="eafdd-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="eafdd-110">제공 된 이름이 목록에 있는 어셈블리의 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eafdd-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eafdd-111">설명</span><span class="sxs-lookup"><span data-stu-id="eafdd-111">Remarks</span></span>  
 <span data-ttu-id="eafdd-112">호출 된 [iclrassemblyidentitymanager:: Getclrassemblyreferencelist](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) 의 인스턴스에 대 한 포인터를 가져올 메서드를 `ICLRAssemblyReferenceList`합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdd-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eafdd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eafdd-113">Requirements</span></span>  
 <span data-ttu-id="eafdd-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eafdd-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eafdd-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eafdd-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="eafdd-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eafdd-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eafdd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafdd-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eafdd-118">See Also</span></span>  
 [<span data-ttu-id="eafdd-119">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eafdd-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="eafdd-120">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eafdd-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="eafdd-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eafdd-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
