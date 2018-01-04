---
title: "GetHashFromHandle 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromHandle
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromHandle
helpviewer_keywords: GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45acc02645f45446e37935d7fe7a455f4105d8bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="b4467-102">GetHashFromHandle 함수</span><span class="sxs-lookup"><span data-stu-id="b4467-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="b4467-103">지정된 된 해시 알고리즘을 사용 하 여 지정 된 파일 핸들을 사용 하 여 파일의 내용에 대 한 해시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="b4467-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-104">This function has been deprecated.</span></span> <span data-ttu-id="b4467-105">사용 하 여 [iclrstrongname:: Gethashfromhandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4467-106">구문</span><span class="sxs-lookup"><span data-stu-id="b4467-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4467-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4467-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="b4467-108">[in] 해시할 파일의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b4467-109">[out에서] 해시 알고리즘을 지정 하는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="b4467-110">기본 알고리즘에 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b4467-111">[out] 반환 된 해시 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b4467-112">[in] 요청된 된 최대 크기의 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b4467-113">[out] 반환 된 바이트 단위로 크기 `pbHash`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4467-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4467-114">Requirements</span></span>  
 <span data-ttu-id="b4467-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4467-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4467-116">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b4467-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b4467-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b4467-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4467-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4467-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4467-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4467-119">See Also</span></span>  
 [<span data-ttu-id="b4467-120">GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="b4467-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="b4467-121">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4467-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
