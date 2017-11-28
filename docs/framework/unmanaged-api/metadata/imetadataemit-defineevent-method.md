---
title: "IMetaDataEmit::DefineEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf790ce270565abaf1d91e54c9e3569a50ab3435
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="5f4d6-102">IMetaDataEmit::DefineEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="5f4d6-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="5f4d6-103">지정한 메타 데이터 서명을 사용 하 여 이벤트에 대 한 정의 만들고 해당 이벤트 정의 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="5f4d6-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f4d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f4d6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="5f4d6-106">[in] 대상 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="5f4d6-107">이 역할은 한 `mdTypeDef` 또는 `mdTypeDefNil` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="5f4d6-108">[in] 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="5f4d6-109">[in] 이벤트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="5f4d6-110">[in] 이벤트 클래스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-110">[in] The token for the event class.</span></span> <span data-ttu-id="5f4d6-111">이 한 `mdTypeDef`, `mdTypeRef`, 또는 `mdTokenNil` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="5f4d6-112">[in] 이벤트 또는 null에 가입 하는 데 사용 되는 메서드.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="5f4d6-113">[in] 이벤트 또는 null를 등록 취소 하는 데 사용 되는 메서드.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="5f4d6-114">[in] 이벤트를 발생 시키는 (파생된 클래스)에 의해 사용 되는 메서드.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="5f4d6-115">[in] 이벤트와 연결 된 다른 방법에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="5f4d6-116">배열의으로 종료 되는 `mdMethodDefNil` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="5f4d6-117">[out] 이벤트에 할당 된 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f4d6-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f4d6-118">Requirements</span></span>  
 <span data-ttu-id="5f4d6-119">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f4d6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4d6-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f4d6-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f4d6-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5f4d6-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f4d6-122">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4d6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f4d6-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f4d6-123">See Also</span></span>  
 [<span data-ttu-id="5f4d6-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f4d6-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5f4d6-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f4d6-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
