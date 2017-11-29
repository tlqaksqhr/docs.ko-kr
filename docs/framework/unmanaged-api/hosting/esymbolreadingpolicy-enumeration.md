---
title: "ESymbolReadingPolicy 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ESymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ESymbolReadingPolicy
helpviewer_keywords: ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce56486453e88a18ebd9dbb42f30bcfdafcf328e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="06ac9-102">ESymbolReadingPolicy 열거형</span><span class="sxs-lookup"><span data-stu-id="06ac9-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="06ac9-103">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac9-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ac9-104">구문</span><span class="sxs-lookup"><span data-stu-id="06ac9-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="06ac9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="06ac9-105">Members</span></span>  
  
|<span data-ttu-id="06ac9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="06ac9-106">Member</span></span>|<span data-ttu-id="06ac9-107">설명</span><span class="sxs-lookup"><span data-stu-id="06ac9-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="06ac9-108">디버거 PDB 파일을 항상 읽을 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac9-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="06ac9-109">디버거는 읽기 전용 완전 신뢰 어셈블리와 관련 된 PDB 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac9-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="06ac9-110">디버거에 PDB 파일을 읽지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac9-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06ac9-111">설명</span><span class="sxs-lookup"><span data-stu-id="06ac9-111">Remarks</span></span>  
 <span data-ttu-id="06ac9-112">`ESymbolReadingPolicy` 열거형 사용한는 [iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="06ac9-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ac9-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06ac9-113">Requirements</span></span>  
 <span data-ttu-id="06ac9-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ac9-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06ac9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06ac9-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06ac9-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06ac9-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ac9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ac9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06ac9-118">See Also</span></span>  
 [<span data-ttu-id="06ac9-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="06ac9-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
