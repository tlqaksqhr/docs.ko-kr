---
title: "IMetaDataImport::GetInterfaceImplProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetInterfaceImplProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0843c9823ba40944e6ea075d469f9a76510d8714
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="01857-102">IMetaDataImport::GetInterfaceImplProps 메서드</span><span class="sxs-lookup"><span data-stu-id="01857-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="01857-103">에 대 한 메타 데이터 토큰에 대 한 포인터를 가져옵니다는 <xref:System.Type> 지정된 된 메서드를 구현 하 고 해당 메서드를 선언 하는 인터페이스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="01857-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01857-104">구문</span><span class="sxs-lookup"><span data-stu-id="01857-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01857-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01857-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="01857-106">[in] 에 대 한 클래스 및 인터페이스 토큰을 반환 하는 메서드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="01857-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="01857-107">[out] 메서드를 구현 하는 클래스를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="01857-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="01857-108">[out] 구현 된 메서드를 정의 하는 인터페이스를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="01857-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01857-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01857-109">Requirements</span></span>  
 <span data-ttu-id="01857-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01857-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01857-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="01857-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01857-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="01857-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01857-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01857-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01857-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01857-114">See Also</span></span>  
 [<span data-ttu-id="01857-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01857-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="01857-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01857-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
