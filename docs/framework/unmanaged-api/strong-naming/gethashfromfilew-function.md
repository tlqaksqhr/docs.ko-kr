---
title: "GetHashFromFileW 함수"
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
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7d62526a6ac9bb06a7de8287c9687933402bfb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="ef5cb-102">GetHashFromFileW 함수</span><span class="sxs-lookup"><span data-stu-id="ef5cb-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="ef5cb-103">유니코드 문자열에 의해 지정 된 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="ef5cb-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-104">This function has been deprecated.</span></span> <span data-ttu-id="ef5cb-105">사용 하 여 [iclrstrongname:: Gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef5cb-106">구문</span><span class="sxs-lookup"><span data-stu-id="ef5cb-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef5cb-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef5cb-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ef5cb-108">[in] 해시 파일의 유니코드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ef5cb-109">[out에서] 해시를 생성할 때 사용 하는 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="ef5cb-110">유효한 알고리즘은 Win32 CryptoAPI에 의해 정의 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="ef5cb-111">경우 `piHashAlg` CALG_SHA-1은 사용 되는 기본 알고리즘 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ef5cb-112">[out] 생성된 된 해시를 포함 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ef5cb-113">[in] 가 가리키는 버퍼의 최대 크기 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ef5cb-114">[out] 를 바이트 단위로 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef5cb-115">설명</span><span class="sxs-lookup"><span data-stu-id="ef5cb-115">Remarks</span></span>  
 <span data-ttu-id="ef5cb-116">이 함수는 동일 [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)제외 하 고 파일 이름 지정이 ANSI 대신 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef5cb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef5cb-117">Requirements</span></span>  
 <span data-ttu-id="ef5cb-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5cb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef5cb-119">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ef5cb-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ef5cb-120">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ef5cb-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef5cb-121">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef5cb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef5cb-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef5cb-122">See Also</span></span>  
 [<span data-ttu-id="ef5cb-123">GetHashFromFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="ef5cb-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="ef5cb-124">GetHashFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="ef5cb-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="ef5cb-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef5cb-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
