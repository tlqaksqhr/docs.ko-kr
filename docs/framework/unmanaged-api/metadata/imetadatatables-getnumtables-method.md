---
title: "IMetaDataTables::GetNumTables 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNumTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 23aa78f8daf649c4fdba218cdc964e4e47070580
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="c00d1-102">IMetaDataTables::GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="c00d1-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="c00d1-103">현재 범위에 테이블의 수를 가져옵니다 `IMetaDataTables` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c00d1-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="c00d1-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c00d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c00d1-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="c00d1-106">[out] 현재 인스턴스 범위에서 테이블의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c00d1-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00d1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c00d1-107">Requirements</span></span>  
 <span data-ttu-id="c00d1-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c00d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00d1-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c00d1-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c00d1-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c00d1-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c00d1-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00d1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c00d1-112">See Also</span></span>  
 [<span data-ttu-id="c00d1-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c00d1-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="c00d1-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c00d1-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
