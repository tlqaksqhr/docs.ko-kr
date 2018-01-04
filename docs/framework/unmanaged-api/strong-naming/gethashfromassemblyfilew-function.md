---
title: "GetHashFromAssemblyFileW 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromAssemblyFileW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromAssemblyFileW
helpviewer_keywords: GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 938d7b5633a73aafb81b16fd2fa207160cac4e05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="50c31-102">GetHashFromAssemblyFileW 함수</span><span class="sxs-lookup"><span data-stu-id="50c31-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="50c31-103">지정된 된 해시 알고리즘을 사용 하 여 지정 된 어셈블리 파일의 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="50c31-104">어셈블리 파일의 경로를 유니코드 문자열로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="50c31-105">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-105">This function has been deprecated.</span></span> <span data-ttu-id="50c31-106">사용 하 여 [iclrstrongname:: Gethashfromassemblyfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50c31-107">구문</span><span class="sxs-lookup"><span data-stu-id="50c31-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50c31-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50c31-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="50c31-109">[in] 해시할 파일에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="50c31-110">이 매개 변수는 유니코드 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="50c31-111">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="50c31-112">기본 해시 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="50c31-113">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="50c31-114">[in] 요청된 된 최대 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="50c31-115">[out] 크기를 바이트 단위로 반환 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50c31-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50c31-116">Requirements</span></span>  
 <span data-ttu-id="50c31-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50c31-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50c31-118">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="50c31-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="50c31-119">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="50c31-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50c31-120">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50c31-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50c31-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50c31-121">See Also</span></span>  
 [<span data-ttu-id="50c31-122">GetHashFromAssemblyFileW 메서드</span><span class="sxs-lookup"><span data-stu-id="50c31-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="50c31-123">GetHashFromAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="50c31-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="50c31-124">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50c31-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
