---
title: "IMetaDataAssemblyImport::CloseEnum 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.CloseEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a0e015d59ff82c4baa3cefd4a32f393f518f291
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="c8d7b-102">IMetaDataAssemblyImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="c8d7b-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="c8d7b-103">지정 된 열거형 인스턴스에 대 한 참조를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d7b-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8d7b-104">Syntax</span></span>  
  
```  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8d7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8d7b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c8d7b-106">[in] 닫을 수 있게 열거형 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="c8d7b-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d7b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8d7b-107">Requirements</span></span>  
 <span data-ttu-id="c8d7b-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d7b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d7b-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c8d7b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8d7b-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c8d7b-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8d7b-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8d7b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d7b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8d7b-112">See Also</span></span>  
 [<span data-ttu-id="c8d7b-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8d7b-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
