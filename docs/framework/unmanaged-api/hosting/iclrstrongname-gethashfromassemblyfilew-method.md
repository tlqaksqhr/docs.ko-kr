---
title: "ICLRStrongName::GetHashFromAssemblyFileW 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFileW
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 14b4e6dae97777873f458018acdaf0c3f5d4f070
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="15085-102">ICLRStrongName::GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="15085-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="15085-103">유니코드 문자열에 의해 지정 된 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="15085-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15085-104">구문</span><span class="sxs-lookup"><span data-stu-id="15085-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15085-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15085-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="15085-106">[in] 해시할 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="15085-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="15085-107">이 매개 변수는 유니코드 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15085-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="15085-108">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="15085-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="15085-109">기본 해시 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15085-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="15085-110">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="15085-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="15085-111">[in] 요청된 된 최대 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="15085-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="15085-112">[out] 크기를 바이트 단위로 반환 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="15085-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15085-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="15085-113">Return Value</span></span>  
 <span data-ttu-id="15085-114">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="15085-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15085-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15085-115">Requirements</span></span>  
 <span data-ttu-id="15085-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15085-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15085-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="15085-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15085-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="15085-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15085-119">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15085-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15085-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15085-120">See Also</span></span>  
 [<span data-ttu-id="15085-121">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="15085-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="15085-122">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15085-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
