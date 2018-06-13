---
title: LoadStringRC 함수
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 463bcf451574700d02f933d024ea5c24cedd259d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441817"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="b1aa3-102">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="b1aa3-102">LoadStringRC Function</span></span>
<span data-ttu-id="b1aa3-103">현재 스레드의 기본 문화권을 사용 하 여 오류 메시지에는 HRESULT 값을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="b1aa3-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1aa3-105">구문</span><span class="sxs-lookup"><span data-stu-id="b1aa3-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1aa3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1aa3-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="b1aa3-107">[in] HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="b1aa3-108">[out] 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="b1aa3-109">[in] 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="b1aa3-110">[in] 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1aa3-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b1aa3-111">Return Value</span></span>  
 <span data-ttu-id="b1aa3-112">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="b1aa3-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="b1aa3-113">Return code</span></span>|<span data-ttu-id="b1aa3-114">설명</span><span class="sxs-lookup"><span data-stu-id="b1aa3-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b1aa3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1aa3-115">S_OK</span></span>|<span data-ttu-id="b1aa3-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="b1aa3-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b1aa3-117">E_INVALIDARG</span></span>|<span data-ttu-id="b1aa3-118">`szBuffer` null 또는 `iMax` 은 영 (0).</span><span class="sxs-lookup"><span data-stu-id="b1aa3-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1aa3-119">설명</span><span class="sxs-lookup"><span data-stu-id="b1aa3-119">Remarks</span></span>  
 <span data-ttu-id="b1aa3-120">메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1aa3-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1aa3-121">Requirements</span></span>  
 <span data-ttu-id="b1aa3-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1aa3-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b1aa3-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1aa3-124">**라이브러리:** 방법으로 MSCorEE.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="b1aa3-125">올바른 버전의.NET Framework를 대상 하는 데 Mscorwks.dll 대신 MSCorEE.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b1aa3-126">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1aa3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1aa3-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1aa3-127">See Also</span></span>  
 [<span data-ttu-id="b1aa3-128">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="b1aa3-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [<span data-ttu-id="b1aa3-129">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="b1aa3-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
