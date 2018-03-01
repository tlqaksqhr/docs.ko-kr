---
title: "LoadStringRCEx 함수"
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
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b046387b5ae365ece694509b302f7ac3a7e066a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="40dd0-102">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="40dd0-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="40dd0-103">HRESULT 값을 지정된 된 문화권에 대 한 적절 한 오류 메시지를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="40dd0-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40dd0-105">구문</span><span class="sxs-lookup"><span data-stu-id="40dd0-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40dd0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40dd0-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="40dd0-107">[in] 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-107">[in] A culture identifier.</span></span> <span data-ttu-id="40dd0-108">-1을 전달 `lcid` 기본 문화권을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="40dd0-109">[in] HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="40dd0-110">[out] 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="40dd0-111">[in] 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="40dd0-112">[in] 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="40dd0-113">[out] 오류 메시지의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40dd0-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="40dd0-114">Return Value</span></span>  
 <span data-ttu-id="40dd0-115">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="40dd0-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="40dd0-116">Return code</span></span>|<span data-ttu-id="40dd0-117">설명</span><span class="sxs-lookup"><span data-stu-id="40dd0-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="40dd0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="40dd0-118">S_OK</span></span>|<span data-ttu-id="40dd0-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="40dd0-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="40dd0-120">E_INVALIDARG</span></span>|<span data-ttu-id="40dd0-121">`szBuffer`매개 변수가 null 이면 또는 `iMax` 은 영 (0).</span><span class="sxs-lookup"><span data-stu-id="40dd0-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40dd0-122">설명</span><span class="sxs-lookup"><span data-stu-id="40dd0-122">Remarks</span></span>  
 <span data-ttu-id="40dd0-123">메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40dd0-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40dd0-124">Requirements</span></span>  
 <span data-ttu-id="40dd0-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40dd0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40dd0-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40dd0-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40dd0-127">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40dd0-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40dd0-128">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40dd0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40dd0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40dd0-129">See Also</span></span>  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="40dd0-130">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="40dd0-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [<span data-ttu-id="40dd0-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="40dd0-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
