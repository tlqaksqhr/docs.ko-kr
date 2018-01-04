---
title: "IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e13211a43c42d66fccd88473c8f881b9edd071d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="14a91-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="14a91-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="14a91-103">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-103">This method is not implemented.</span></span> <span data-ttu-id="14a91-104">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a91-105">구문</span><span class="sxs-lookup"><span data-stu-id="14a91-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14a91-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14a91-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="14a91-107">[in] 에 대 한 포인터는 [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) 를 범위를 열 형식 정보를 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-107">[in] Pointer to an [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="14a91-108">[in] 열기 모드 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="14a91-109">[in] 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="14a91-110">[out] 반환 되는 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14a91-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14a91-111">Requirements</span></span>  
 <span data-ttu-id="14a91-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14a91-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14a91-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="14a91-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="14a91-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="14a91-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="14a91-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14a91-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a91-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14a91-116">See Also</span></span>  
 [<span data-ttu-id="14a91-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14a91-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="14a91-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14a91-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
