---
title: "LoadStringRC 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRC
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRC
helpviewer_keywords: LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fd42a576e1315ea029f98b94d8dc84d2b92b5e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrc-function"></a><span data-ttu-id="29935-102">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="29935-102">LoadStringRC Function</span></span>
<span data-ttu-id="29935-103">현재 스레드의 기본 문화권을 사용 하 여 오류 메시지에는 HRESULT 값을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="29935-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29935-105">구문</span><span class="sxs-lookup"><span data-stu-id="29935-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29935-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29935-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="29935-107">[in] HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="29935-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="29935-108">[out] 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="29935-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="29935-109">[in] 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="29935-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="29935-110">[in] 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29935-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29935-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="29935-111">Return Value</span></span>  
 <span data-ttu-id="29935-112">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="29935-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="29935-113">Return code</span></span>|<span data-ttu-id="29935-114">설명</span><span class="sxs-lookup"><span data-stu-id="29935-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="29935-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="29935-115">S_OK</span></span>|<span data-ttu-id="29935-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="29935-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="29935-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="29935-117">E_INVALIDARG</span></span>|<span data-ttu-id="29935-118">`szBuffer`null 또는 `iMax` 은 영 (0).</span><span class="sxs-lookup"><span data-stu-id="29935-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29935-119">설명</span><span class="sxs-lookup"><span data-stu-id="29935-119">Remarks</span></span>  
 <span data-ttu-id="29935-120">메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29935-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29935-121">Requirements</span></span>  
 <span data-ttu-id="29935-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29935-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29935-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29935-124">**라이브러리:** 방법으로 MSCorEE.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="29935-125">올바른 버전의.NET Framework를 대상 하는 데 Mscorwks.dll 대신 MSCorEE.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="29935-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="29935-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29935-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29935-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29935-127">See Also</span></span>  
 [<span data-ttu-id="29935-128">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="29935-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [<span data-ttu-id="29935-129">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="29935-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
