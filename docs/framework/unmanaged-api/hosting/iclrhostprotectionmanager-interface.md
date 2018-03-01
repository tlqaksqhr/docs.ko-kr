---
title: "ICLRHostProtectionManager 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37b1aaeef1d4c375f36ad043124287fc3b41e3fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="abf38-102">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="abf38-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="abf38-103">호스트를에서 특정 관리 되는 클래스, 메서드, 속성 및 부분적으로 신뢰할 수 있는 코드에서 실행 되는 필드를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abf38-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abf38-104">메서드</span><span class="sxs-lookup"><span data-stu-id="abf38-104">Methods</span></span>  
  
|<span data-ttu-id="abf38-105">메서드</span><span class="sxs-lookup"><span data-stu-id="abf38-105">Method</span></span>|<span data-ttu-id="abf38-106">설명</span><span class="sxs-lookup"><span data-stu-id="abf38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="abf38-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="abf38-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="abf38-108">치명적인 공용 언어 런타임 (CLR) 오류가 발생할 수 있는 경합 상태가 발생 하지 않도록 합니다 보증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="abf38-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="abf38-109">SetProtectedCategories 메서드</span><span class="sxs-lookup"><span data-stu-id="abf38-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="abf38-110">관리 되는 형식 및 부분적으로 신뢰할 수 있는 코드에서 실행에서 차단 해야 하는 멤버의 범주를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abf38-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="abf38-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="abf38-111">Requirements</span></span>  
 <span data-ttu-id="abf38-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="abf38-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf38-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="abf38-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abf38-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="abf38-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abf38-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf38-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf38-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abf38-116">See Also</span></span>  
 [<span data-ttu-id="abf38-117">EApiCategories 열거형</span><span class="sxs-lookup"><span data-stu-id="abf38-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="abf38-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="abf38-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
