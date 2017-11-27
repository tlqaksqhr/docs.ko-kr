---
title: "ISymUnmanagedReader::GetSymAttribute 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymAttribute
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f57d2c4541945d90b1695850311928884fdc9cc5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="6b427-102">ISymUnmanagedReader::GetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="6b427-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="6b427-103">이름을 기반으로 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="6b427-104">사용자 지정 특성 메타 데이터와는 달리 이러한 사용자 지정 특성 기호 저장소에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b427-105">구문</span><span class="sxs-lookup"><span data-stu-id="6b427-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b427-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b427-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="6b427-107">[in] 특성이 요청 된 개체에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="6b427-108">[in] 검색할 특성을 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="6b427-109">[in] `buffer` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="6b427-110">[out] 특성 데이터의 길이 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="6b427-111">[out] 특성 데이터를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b427-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="6b427-112">Return Value</span></span>  
 <span data-ttu-id="6b427-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6b427-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b427-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b427-114">Requirements</span></span>  
 <span data-ttu-id="6b427-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6b427-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b427-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b427-116">See Also</span></span>  
 [<span data-ttu-id="6b427-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b427-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
