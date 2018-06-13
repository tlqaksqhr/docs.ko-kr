---
title: GetHistoryFileDirectory 함수
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba40acf7bfd20897ece4de285fe7a9175be83e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431765"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="dcf56-102">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="dcf56-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="dcf56-103">응용 프로그램 기록 디렉터리의 경로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf56-104">구문</span><span class="sxs-lookup"><span data-stu-id="dcf56-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcf56-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dcf56-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="dcf56-106">[out] 응용 프로그램 기록 디렉터리 경로 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="dcf56-107">[out에서] 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcf56-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="dcf56-108">Return Value</span></span>  
 <span data-ttu-id="dcf56-109">이 메서드는 다음 값 외에도 WinError.h 파일에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="dcf56-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="dcf56-110">Return code</span></span>|<span data-ttu-id="dcf56-111">설명</span><span class="sxs-lookup"><span data-stu-id="dcf56-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="dcf56-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="dcf56-112">S_OK</span></span>|<span data-ttu-id="dcf56-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="dcf56-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dcf56-114">E_INVALIDARG</span></span>|<span data-ttu-id="dcf56-115">`wzDir` 또는 `pdwSize` null 또는 버전 문자열이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcf56-116">설명</span><span class="sxs-lookup"><span data-stu-id="dcf56-116">Remarks</span></span>  
 <span data-ttu-id="dcf56-117">성공적으로 완료 되는 `pdwSize` 경로 문자열의 길이 인수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf56-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcf56-118">Requirements</span></span>  
 <span data-ttu-id="dcf56-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf56-120">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="dcf56-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dcf56-121">**라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="dcf56-122">올바른 버전의.NET Framework를 대상 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf56-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="dcf56-123">**.NET framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf56-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf56-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcf56-124">See Also</span></span>  
 [<span data-ttu-id="dcf56-125">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="dcf56-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="dcf56-126">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="dcf56-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="dcf56-127">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="dcf56-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
