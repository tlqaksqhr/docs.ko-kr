---
title: "IMetaDataConverter::GetTypeLibFromMetaData 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter.GetTypeLibFromMetaData
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b2b12c5f3ecb0d30fad3bfb5c96e0e66fd9ee7bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="88d37-102">IMetaDataConverter::GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="88d37-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="88d37-103">에 대 한 포인터를 가져옵니다는 `ITypeLib` 라이브러리 및 모듈 이름이 지정 된 형식 라이브러리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="88d37-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88d37-104">구문</span><span class="sxs-lookup"><span data-stu-id="88d37-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88d37-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88d37-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="88d37-106">[in] 형식 라이브러리 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88d37-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="88d37-107">[in] 형식 라이브러리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="88d37-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="88d37-108">[out] 주소를 받는 위치에 대 한 포인터는 `ITypeLib` 형식 라이브러리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="88d37-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88d37-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88d37-109">Requirements</span></span>  
 <span data-ttu-id="88d37-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88d37-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88d37-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88d37-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88d37-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="88d37-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88d37-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88d37-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d37-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88d37-114">See Also</span></span>  
 [<span data-ttu-id="88d37-115">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88d37-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
