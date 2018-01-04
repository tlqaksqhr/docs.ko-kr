---
title: "IMapToken::Map 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMapToken.Map
api_location: mscoree.dll
api_type: COM
f1_keywords: IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe034d2bc6d70e820fa3ad5de8140afa9a19a6bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="b5938-102">IMapToken::Map 메서드</span><span class="sxs-lookup"><span data-stu-id="b5938-102">IMapToken::Map Method</span></span>
<span data-ttu-id="b5938-103">메타 데이터 서명을 사용 하 여 어셈블리 간의 관계를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b5938-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5938-104">구문</span><span class="sxs-lookup"><span data-stu-id="b5938-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5938-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5938-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="b5938-106">[in] 가져온된 코드 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b5938-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="b5938-107">[in] 내보낸된 코드 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b5938-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5938-108">설명</span><span class="sxs-lookup"><span data-stu-id="b5938-108">Remarks</span></span>  
 <span data-ttu-id="b5938-109">병합 하는 동안 발생 토큰 다시 매핑 가져온된 (원본) 메타 데이터 범위에서 원래 토큰 범위 지정 및 내보낸된 (대상) 메타 데이터 범위에서 새 토큰 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5938-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5938-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5938-110">Requirements</span></span>  
 <span data-ttu-id="b5938-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5938-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5938-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5938-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5938-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b5938-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5938-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5938-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5938-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5938-115">See Also</span></span>  
 [<span data-ttu-id="b5938-116">IMapToken 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b5938-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
