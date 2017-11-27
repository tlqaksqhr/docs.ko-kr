---
title: "IMetaDataImport2::EnumMethodSpecs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db1968c73d5a1c6e0687bc86f249c70b6c21712c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="ff941-102">IMetaDataImport2::EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="ff941-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="ff941-103">지정한 MethodDef 또는 MemberRef 연관 MethodSpec 토큰 배열의 토큰 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff941-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff941-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff941-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff941-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ff941-106">[out에서] 에 대 한 열거자에 대 한 포인터 `rMethodSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="ff941-107">[in] MethodDef 또는 MemberRef 토큰을 열거할 수 있는 MethodSpec 토큰은 메서드를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="ff941-108">하는 경우의 값 `tk` 0 (영) 이면 범위에서 모든 MethodSpec 토큰을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="ff941-109">[out] 열거할 MethodSpec 토큰이의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ff941-110">[in] 요청 된 최대 수에 배치 하는 토큰의 `rMethodSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="ff941-111">[out] 반환 된 토큰 수에 배치 `rMethodSpecs`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff941-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff941-112">Return Value</span></span>  
  
|<span data-ttu-id="ff941-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff941-113">HRESULT</span></span>|<span data-ttu-id="ff941-114">설명</span><span class="sxs-lookup"><span data-stu-id="ff941-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ff941-115">`EnumMethodSpecs`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ff941-116">`phEnum`에 멤버가 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="ff941-117">이 경우 `pcMethodSpecs` 0 (영)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff941-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff941-118">Requirements</span></span>  
 <span data-ttu-id="ff941-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff941-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff941-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff941-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff941-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="ff941-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff941-122">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff941-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff941-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff941-123">See Also</span></span>  
 [<span data-ttu-id="ff941-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff941-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="ff941-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff941-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
