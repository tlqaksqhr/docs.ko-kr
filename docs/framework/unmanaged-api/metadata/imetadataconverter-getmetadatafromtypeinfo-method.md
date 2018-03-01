---
title: "IMetaDataConverter::GetMetaDataFromTypeInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66e090efc9ce8a8fc1ca5de8d8f7a60f9ca17b9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="8aefe-102">IMetaDataConverter::GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="8aefe-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="8aefe-103">에 대 한 포인터를 가져옵니다는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 에서 지정 된 참조 형식 라이브러리의 메타 데이터 서명을 나타내는 인스턴스는 `ITypeInfo` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8aefe-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aefe-104">구문</span><span class="sxs-lookup"><span data-stu-id="8aefe-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8aefe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8aefe-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="8aefe-106">[in] 에 대 한 포인터는 `ITypeInfo` 형식 라이브러리를 참조 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8aefe-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="8aefe-107">[out] 주소를 받는 위치에 대 한 포인터는 `IMetaDataImport` 메타 데이터 서명을 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8aefe-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aefe-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8aefe-108">Requirements</span></span>  
 <span data-ttu-id="8aefe-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8aefe-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aefe-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8aefe-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8aefe-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="8aefe-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8aefe-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aefe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aefe-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aefe-113">See Also</span></span>  
 [<span data-ttu-id="8aefe-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aefe-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8aefe-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aefe-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
