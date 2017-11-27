---
title: "ICorPublishAppDomain::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9807f914c767cc212bf97d83042e76d42a3d9440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="0d676-102">ICorPublishAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="0d676-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="0d676-103">이 표시 되는 응용 프로그램 도메인의 이름을 가져옵니다 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d676-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d676-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d676-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d676-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0d676-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0d676-107">[out] 반환 된 null 문자를 포함 하는 와이드 문자 수에 대 한 포인터는 `szName` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="0d676-108">[out] 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d676-109">설명</span><span class="sxs-lookup"><span data-stu-id="0d676-109">Remarks</span></span>  
 <span data-ttu-id="0d676-110">경우 `szName` 은 null이 아니며는 `GetName` 메서드 최대 복사 `cchName` 까지의 문자 (null 종결자 포함) `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="0d676-111">Null이 아닌 반환 되는 `pcchName`을 실제 이름 (null 종결자 포함)에 문자 수에 저장 됩니다는 `szName` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="0d676-112">`GetName` 메서드 복사 된 문자 수에 관계 없이 s_ok이 고 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d676-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d676-113">Requirements</span></span>  
 <span data-ttu-id="0d676-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d676-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d676-115">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0d676-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0d676-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d676-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d676-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d676-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d676-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d676-118">See Also</span></span>  
 [<span data-ttu-id="0d676-119">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d676-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
