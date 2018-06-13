---
title: ICLRStrongName::GetHashFromBlob 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a489e05435ce160c65e936f448688d69b3a965f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435263"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="3d5ab-102">ICLRStrongName::GetHashFromBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="3d5ab-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="3d5ab-103">지정된 된 해시 알고리즘을 사용 하 여 지정 된 메모리 주소에서 어셈블리의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d5ab-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3d5ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d5ab-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="3d5ab-106">[in] 해시할 메모리 블록의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="3d5ab-107">[in] 메모리 블록의 길이 (바이트)를 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3d5ab-108">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="3d5ab-109">기본 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3d5ab-110">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3d5ab-111">[in] 요청된 된 최대 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3d5ab-112">[out] 반환 된 바이트 단위로 크기 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d5ab-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="3d5ab-113">Return Value</span></span>  
 <span data-ttu-id="3d5ab-114">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="3d5ab-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d5ab-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d5ab-115">Requirements</span></span>  
 <span data-ttu-id="3d5ab-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d5ab-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d5ab-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3d5ab-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3d5ab-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3d5ab-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d5ab-119">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d5ab-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5ab-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d5ab-120">See Also</span></span>  
 [<span data-ttu-id="3d5ab-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d5ab-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
