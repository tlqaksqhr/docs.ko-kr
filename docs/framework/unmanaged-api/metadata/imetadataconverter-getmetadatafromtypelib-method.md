---
title: "IMetaDataConverter::GetMetaDataFromTypeLib 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter.GetMetaDataFromTypeLib
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74197e3195d96a0bb353d48ed3d57a15b40f461c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="69670-102">IMetaDataConverter::GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="69670-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="69670-103">한 인터페이스 포인터를 가져옵니다는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 를 지정 된 형식 라이브러리의 메타 데이터 서명을 나타내는 `ITypeLib` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="69670-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69670-104">구문</span><span class="sxs-lookup"><span data-stu-id="69670-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69670-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69670-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="69670-106">[in] 에 대 한 포인터는 `ITypeLib` 형식 라이브러리를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="69670-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="69670-107">[out] 주소를 받는 위치에 대 한 포인터는 `IMetaDataImport` 메타 데이터 서명을 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="69670-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69670-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69670-108">Requirements</span></span>  
 <span data-ttu-id="69670-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69670-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69670-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69670-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69670-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="69670-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69670-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69670-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69670-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69670-113">See Also</span></span>  
 [<span data-ttu-id="69670-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69670-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="69670-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69670-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
