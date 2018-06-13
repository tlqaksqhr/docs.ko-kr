---
title: StrongNameFreeBuffer 함수
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a129608370cd72967e0c441eff12b4aca7e638c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455090"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="9d0cb-102">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="9d0cb-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="9d0cb-103">와 같은 강력한 이름 함수에 대 한 이전 호출을 사용 하 여 할당 된 메모리를 확보 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), 또는 [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="9d0cb-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="9d0cb-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d0cb-104">This function has been deprecated.</span></span> <span data-ttu-id="9d0cb-105">사용 하 여 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0cb-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d0cb-106">구문</span><span class="sxs-lookup"><span data-stu-id="9d0cb-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d0cb-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d0cb-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="9d0cb-108">[in] 메모리를 해제에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9d0cb-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d0cb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d0cb-109">Requirements</span></span>  
 <span data-ttu-id="9d0cb-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d0cb-111">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9d0cb-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9d0cb-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9d0cb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d0cb-113">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d0cb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d0cb-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d0cb-114">See Also</span></span>  
 [<span data-ttu-id="9d0cb-115">StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="9d0cb-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
 [<span data-ttu-id="9d0cb-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d0cb-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
