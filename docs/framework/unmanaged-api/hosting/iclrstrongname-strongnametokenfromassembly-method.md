---
title: "ICLRStrongName::StrongNameTokenFromAssembly 메서드"
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
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 455a04c3c5465ec263c5d2131ac8f3c4e34ea610
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="4a6d4-102">ICLRStrongName::StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="4a6d4-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="4a6d4-103">지정한 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a6d4-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a6d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a6d4-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4a6d4-106">[in] 경로 어셈블리에 대 한 이식 가능한 실행 (PE) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="4a6d4-107">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="4a6d4-108">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a6d4-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="4a6d4-109">Return Value</span></span>  
 <span data-ttu-id="4a6d4-110">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="4a6d4-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a6d4-111">설명</span><span class="sxs-lookup"><span data-stu-id="4a6d4-111">Remarks</span></span>  
 <span data-ttu-id="4a6d4-112">강력한 이름 토큰에는 공개 키의 축약 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="4a6d4-113">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="4a6d4-114">어셈블리에 대 한 강력한 이름의 일부인 토큰과 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="4a6d4-115">호출 해야 토큰을 만든 후의 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6d4-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a6d4-116">Requirements</span></span>  
 <span data-ttu-id="4a6d4-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6d4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6d4-118">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4a6d4-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4a6d4-119">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4a6d4-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a6d4-120">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6d4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6d4-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a6d4-121">See Also</span></span>  
 [<span data-ttu-id="4a6d4-122">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="4a6d4-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="4a6d4-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a6d4-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
