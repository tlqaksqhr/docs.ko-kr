---
title: "ICLRStrongName::GetHashFromAssemblyFile 메서드"
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
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6dcb0ca16c2ffdd8a928cec9cca44b628de34885
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="5d43a-102">ICLRStrongName::GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="5d43a-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="5d43a-103">지정된 된 해시 알고리즘을 사용 하 여 지정 된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d43a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d43a-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d43a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d43a-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="5d43a-106">[in] 해시할 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5d43a-107">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5d43a-108">기본 해시 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5d43a-109">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5d43a-110">[in] 요청된 된 최대 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5d43a-111">[out] 크기를 바이트 단위로 반환 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d43a-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="5d43a-112">Return Value</span></span>  
 <span data-ttu-id="5d43a-113">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="5d43a-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d43a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d43a-114">Requirements</span></span>  
 <span data-ttu-id="5d43a-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d43a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d43a-116">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5d43a-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5d43a-117">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5d43a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d43a-118">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d43a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d43a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d43a-119">See Also</span></span>  
 [<span data-ttu-id="5d43a-120">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="5d43a-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="5d43a-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d43a-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
