---
title: EInitializeNewDomainFlags 열거형
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0175ab1d06a8166a5bbfd0c42018085a801740f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431451"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="aaeb5-102">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="aaeb5-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="aaeb5-103">런타임에 응용 프로그램 도메인의 초기화에 대 한 정보를 제공 하기 위해 호스트를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaeb5-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaeb5-104">구문</span><span class="sxs-lookup"><span data-stu-id="aaeb5-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="aaeb5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="aaeb5-105">Members</span></span>  
  
|<span data-ttu-id="aaeb5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="aaeb5-106">Member</span></span>|<span data-ttu-id="aaeb5-107">설명</span><span class="sxs-lookup"><span data-stu-id="aaeb5-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="aaeb5-108">플래그가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aaeb5-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="aaeb5-109">호스트에서 응용 프로그램 도메인의 보안 상태를 변경 하면 안 됩니다 공용 언어 런타임 (CLR) 알립니다는 <xref:System.AppDomainManager.InitializeNewDomain%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="aaeb5-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaeb5-110">설명</span><span class="sxs-lookup"><span data-stu-id="aaeb5-110">Remarks</span></span>  
 <span data-ttu-id="aaeb5-111">[iclrdomainmanager:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) 형식의 매개 변수를 사용 하는 메서드 `EInitializeNewDomainFlags`합니다.</span><span class="sxs-lookup"><span data-stu-id="aaeb5-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaeb5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aaeb5-112">Requirements</span></span>  
 <span data-ttu-id="aaeb5-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aaeb5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaeb5-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aaeb5-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aaeb5-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aaeb5-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aaeb5-116">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaeb5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaeb5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aaeb5-117">See Also</span></span>  
 [<span data-ttu-id="aaeb5-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="aaeb5-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="aaeb5-119">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="aaeb5-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
