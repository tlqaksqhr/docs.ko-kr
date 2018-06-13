---
title: _EFN_GetManagedObjectName 함수
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f13fad537a6847ba6e19c939e72df86036e28ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402206"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="5792a-102">_EFN_GetManagedObjectName 함수</span><span class="sxs-lookup"><span data-stu-id="5792a-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="5792a-103">제공된 된 관리 되는 개체 포인터를 사용 하는 형식의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5792a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5792a-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5792a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5792a-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="5792a-106">[in] 디버그 클라이언트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="5792a-107">[in] 관리 되는 개체 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="5792a-108">szName</span><span class="sxs-lookup"><span data-stu-id="5792a-108">szName</span></span>  
 <span data-ttu-id="5792a-109">[out] 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="5792a-110">[out] 문자열 버퍼에서 사용할 수 있는 문자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5792a-111">설명</span><span class="sxs-lookup"><span data-stu-id="5792a-111">Remarks</span></span>  
 <span data-ttu-id="5792a-112">관리 되는 코드가 없는 스레드의 현재 컨텍스트에서 함수 0xa0 시설 값 및 오류 코드 0 x 1000 SOS_E_NOMANAGEDCODE HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5792a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5792a-113">Requirements</span></span>  
 <span data-ttu-id="5792a-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5792a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5792a-115">**헤더:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="5792a-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="5792a-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5792a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5792a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5792a-117">See Also</span></span>  
 [<span data-ttu-id="5792a-118">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5792a-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
