---
title: "IMetaDataError::OnError 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError.OnError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7b8947f0bac8b51e704fbbb9085cf48740b3197d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="3d2b3-102">IMetaDataError::OnError 메서드</span><span class="sxs-lookup"><span data-stu-id="3d2b3-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="3d2b3-103">메타 데이터를 병합 하는 동안 발생 하는 오류에 대 한 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2b3-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d2b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d2b3-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d2b3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d2b3-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="3d2b3-106">[in] 호출 하는 메서드로 반환 된 HRESULT 오류 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2b3-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="3d2b3-107">[in] 오류가 발생할 때 병합 되 고 코드 개체의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2b3-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d2b3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d2b3-108">Requirements</span></span>  
 <span data-ttu-id="3d2b3-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2b3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d2b3-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3d2b3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d2b3-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3d2b3-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d2b3-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d2b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d2b3-113">See Also</span></span>  
 [<span data-ttu-id="3d2b3-114">IMetaDataError 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d2b3-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
