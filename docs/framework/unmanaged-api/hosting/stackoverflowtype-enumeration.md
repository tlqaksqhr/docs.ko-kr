---
title: "StackOverflowType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackOverflowType
api_location: mscoree.dll
api_type: COM
f1_keywords: StackOverflowType
helpviewer_keywords: StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 64312398c95a33c2bbe136b1c4d03c06cb09aeef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="f53de-102">StackOverflowType 열거형</span><span class="sxs-lookup"><span data-stu-id="f53de-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="f53de-103">스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f53de-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53de-104">구문</span><span class="sxs-lookup"><span data-stu-id="f53de-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="f53de-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f53de-105">Members</span></span>  
  
|<span data-ttu-id="f53de-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f53de-106">Member</span></span>|<span data-ttu-id="f53de-107">설명</span><span class="sxs-lookup"><span data-stu-id="f53de-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="f53de-108">실행 엔진으로 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f53de-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="f53de-109">관리 코드로 인해 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f53de-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="f53de-110">비관리 코드로 인해 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f53de-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f53de-111">설명</span><span class="sxs-lookup"><span data-stu-id="f53de-111">Remarks</span></span>  
 <span data-ttu-id="f53de-112">이 정보에 대 한 호출을 통해 호스트에 전달 되는 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f53de-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f53de-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f53de-113">Requirements</span></span>  
 <span data-ttu-id="f53de-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f53de-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f53de-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f53de-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f53de-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f53de-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f53de-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f53de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53de-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f53de-118">See Also</span></span>  
 [<span data-ttu-id="f53de-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="f53de-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
