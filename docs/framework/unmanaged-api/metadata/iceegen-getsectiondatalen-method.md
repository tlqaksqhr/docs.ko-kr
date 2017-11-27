---
title: "ICeeGen::GetSectionDataLen 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionDataLen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7d119fdfe5c0202d08ca78026a6917bb4ef51422
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="2c839-102">ICeeGen::GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="2c839-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="2c839-103">지정된 된 섹션의 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c839-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="2c839-104">이 메서드는 사용 되지 않으며 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c839-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c839-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c839-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c839-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c839-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="2c839-107">[in] 데이터 섹션 길이가 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c839-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="2c839-108">[out] 지정된 된 섹션의 반환 된 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="2c839-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c839-109">설명</span><span class="sxs-lookup"><span data-stu-id="2c839-109">Remarks</span></span>  
 <span data-ttu-id="2c839-110">호출 `GetSectionDataLen` 다른 방법으로 처리 되지 않는 섹션 특별 한 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c839-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c839-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c839-111">Requirements</span></span>  
 <span data-ttu-id="2c839-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2c839-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c839-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c839-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c839-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2c839-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c839-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c839-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c839-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c839-116">See Also</span></span>  
 [<span data-ttu-id="2c839-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c839-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
