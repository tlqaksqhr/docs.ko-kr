---
title: "ICLRStrongName::StrongNameGetBlobFromImage 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameGetBlobFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80edfa333f73854869c3fa6786e038c796b09087
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="7434e-102">ICLRStrongName::StrongNameGetBlobFromImage 메서드</span><span class="sxs-lookup"><span data-stu-id="7434e-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="7434e-103">지정 된 메모리 주소에서 어셈블리 이미지의 이진 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7434e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7434e-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7434e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7434e-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="7434e-106">[in] 매핑된 어셈블리 매니페스트에의 메모리 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7434e-107">[in] 에 있는 이미지를 바이트 단위로 크기 `pbBase`합니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="7434e-108">[in] 이미지의 이진 표현을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="7434e-109">[out에서] 최대 크기를 바이트, 요청 된 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="7434e-110">반환 되 면 실제 크기를 바이트 단위로 `pbBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7434e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7434e-111">Return Value</span></span>  
 <span data-ttu-id="7434e-112">`S_OK`메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값 (참조 [일반적인 HRESULT 값](http://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="7434e-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7434e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7434e-113">Requirements</span></span>  
 <span data-ttu-id="7434e-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7434e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7434e-115">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7434e-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7434e-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7434e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7434e-117">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7434e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7434e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7434e-118">See Also</span></span>  
 [<span data-ttu-id="7434e-119">StrongNameGetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="7434e-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="7434e-120">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7434e-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
