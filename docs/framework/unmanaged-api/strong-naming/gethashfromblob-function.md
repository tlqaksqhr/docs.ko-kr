---
title: "GetHashFromBlob 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromBlob
helpviewer_keywords: GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 360036cd1578c2845f09f92c09d79e44618abe75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="00087-102">GetHashFromBlob 함수</span><span class="sxs-lookup"><span data-stu-id="00087-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="00087-103">지정된 된 해시 알고리즘을 사용 하 여 지정 된 메모리 주소에서 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="00087-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="00087-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00087-104">This function has been deprecated.</span></span> <span data-ttu-id="00087-105">사용 하 여 [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="00087-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00087-106">구문</span><span class="sxs-lookup"><span data-stu-id="00087-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00087-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00087-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="00087-108">[in] 해시할 메모리 블록의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="00087-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="00087-109">[in] 메모리 블록의 길이 (바이트)를 합니다.</span><span class="sxs-lookup"><span data-stu-id="00087-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="00087-110">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="00087-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="00087-111">기본 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="00087-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="00087-112">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="00087-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="00087-113">[in] 요청된 된 최대 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="00087-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="00087-114">[out] 반환 된 바이트 단위로 크기 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="00087-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00087-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00087-115">Requirements</span></span>  
 <span data-ttu-id="00087-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00087-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00087-117">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="00087-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="00087-118">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="00087-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00087-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00087-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00087-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00087-120">See Also</span></span>  
 [<span data-ttu-id="00087-121">GetHashFromBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="00087-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="00087-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00087-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
