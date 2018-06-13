---
title: StrongNameTokenFromAssembly 함수
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f04d71e1709eed6c3a9f1af400f79b4722f4433
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457703"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="5fda4-102">StrongNameTokenFromAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="5fda4-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="5fda4-103">지정한 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="5fda4-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-104">This function has been deprecated.</span></span> <span data-ttu-id="5fda4-105">사용 하 여 [iclrstrongname:: Strongnametokenfromassembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fda4-106">구문</span><span class="sxs-lookup"><span data-stu-id="5fda4-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fda4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5fda4-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5fda4-108">[in] 경로 어셈블리에 대 한 이식 가능한 실행 (PE) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="5fda4-109">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="5fda4-110">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fda4-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="5fda4-111">Return Value</span></span>  
 <span data-ttu-id="5fda4-112">`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fda4-113">설명</span><span class="sxs-lookup"><span data-stu-id="5fda4-113">Remarks</span></span>  
 <span data-ttu-id="5fda4-114">강력한 이름 토큰에는 공개 키의 축약 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="5fda4-115">토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="5fda4-116">어셈블리에 대 한 강력한 이름의 일부인 토큰과 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="5fda4-117">호출 해야 토큰을 만든 후의 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) 함수 할당 된 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="5fda4-118">경우는 `StrongNameTokenFromAssembly` 함수는 성공적으로 완료를 호출 하지는 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 함수를 마지막으로 생성 된 오류를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fda4-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fda4-119">Requirements</span></span>  
 <span data-ttu-id="5fda4-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fda4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fda4-121">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5fda4-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5fda4-122">**라이브러리:** mscoree.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5fda4-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="5fda4-123">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fda4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fda4-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fda4-124">See Also</span></span>  
 [<span data-ttu-id="5fda4-125">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="5fda4-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="5fda4-126">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="5fda4-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="5fda4-127">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5fda4-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
