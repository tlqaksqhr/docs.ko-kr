---
title: "StrongNameGetBlob 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameGetBlob
helpviewer_keywords: StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1948a0d8a8536ebe9b0531eecaf3df446252b0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="98c85-102">StrongNameGetBlob 함수</span><span class="sxs-lookup"><span data-stu-id="98c85-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="98c85-103">지정된 된 주소에서 실행 파일의 이진 표현으로 지정된 된 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="98c85-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-104">This function has been deprecated.</span></span> <span data-ttu-id="98c85-105">사용 하 여 [iclrstrongname:: Strongnamegetblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c85-106">구문</span><span class="sxs-lookup"><span data-stu-id="98c85-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98c85-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98c85-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="98c85-108">[in] 로드할 실행 파일에 유효한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="98c85-109">[in] 실행 파일을 로드할 수 있는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="98c85-110">[out에서] 최대 크기를 바이트, 요청 된 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="98c85-111">반환 되 면 실제 크기를 바이트 단위로 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98c85-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="98c85-112">Return Value</span></span>  
 <span data-ttu-id="98c85-113">`true`성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98c85-114">설명</span><span class="sxs-lookup"><span data-stu-id="98c85-114">Remarks</span></span>  
 <span data-ttu-id="98c85-115">경우는 `StrongNameGetBlob` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98c85-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98c85-116">Requirements</span></span>  
 <span data-ttu-id="98c85-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98c85-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98c85-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="98c85-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="98c85-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="98c85-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98c85-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98c85-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c85-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98c85-121">See Also</span></span>  
 [<span data-ttu-id="98c85-122">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="98c85-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="98c85-123">StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="98c85-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="98c85-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98c85-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
