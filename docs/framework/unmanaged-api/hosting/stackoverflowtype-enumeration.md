---
title: StackOverflowType 열거형
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e888b2359336c68ea6fdf52f798145fda12002e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440871"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="144b3-102">StackOverflowType 열거형</span><span class="sxs-lookup"><span data-stu-id="144b3-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="144b3-103">스택 오버플로 이벤트의 근본 원인을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="144b3-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="144b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="144b3-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="144b3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="144b3-105">Members</span></span>  
  
|<span data-ttu-id="144b3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="144b3-106">Member</span></span>|<span data-ttu-id="144b3-107">설명</span><span class="sxs-lookup"><span data-stu-id="144b3-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="144b3-108">실행 엔진으로 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="144b3-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="144b3-109">관리 코드로 인해 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="144b3-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="144b3-110">비관리 코드로 인해 스택 오버플로가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="144b3-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="144b3-111">설명</span><span class="sxs-lookup"><span data-stu-id="144b3-111">Remarks</span></span>  
 <span data-ttu-id="144b3-112">이 정보에 대 한 호출을 통해 호스트에 전달 되는 [iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="144b3-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="144b3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="144b3-113">Requirements</span></span>  
 <span data-ttu-id="144b3-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="144b3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="144b3-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="144b3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="144b3-116">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="144b3-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="144b3-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="144b3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="144b3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="144b3-118">See Also</span></span>  
 [<span data-ttu-id="144b3-119">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="144b3-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
