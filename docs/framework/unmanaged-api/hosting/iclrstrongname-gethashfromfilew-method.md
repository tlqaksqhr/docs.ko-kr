---
title: "ICLRStrongName::GetHashFromFileW 메서드"
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
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eec58e0cf062e405c757a506e9c26955009b710b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="9d611-102">ICLRStrongName::GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="9d611-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="9d611-103">유니코드 문자열에 의해 지정 된 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d611-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d611-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d611-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d611-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9d611-106">[in] 해시 파일의 유니코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="9d611-107">[out에서] 해시를 생성할 때 사용 하는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="9d611-108">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="9d611-109">경우 `piHashAlg` CALG_SHA-1은 사용 되는 기본 알고리즘 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="9d611-110">[out] 생성된 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="9d611-111">[in] 가 가리키는 버퍼의 최대 크기 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="9d611-112">[out] 를 바이트 단위로 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d611-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="9d611-113">Return Value</span></span>  
 <span data-ttu-id="9d611-114">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="9d611-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d611-115">설명</span><span class="sxs-lookup"><span data-stu-id="9d611-115">Remarks</span></span>  
 <span data-ttu-id="9d611-116">이 메서드는 동일는 [iclrstrongname:: Gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) 메서드를 제외 하는 파일 이름 지정은 ANSI 대신 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d611-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d611-117">Requirements</span></span>  
 <span data-ttu-id="9d611-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d611-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d611-119">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9d611-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d611-120">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9d611-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d611-121">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d611-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d611-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d611-122">See Also</span></span>  
 [<span data-ttu-id="9d611-123">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="9d611-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="9d611-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d611-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
