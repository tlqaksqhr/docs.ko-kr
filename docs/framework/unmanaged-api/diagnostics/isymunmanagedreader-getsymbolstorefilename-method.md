---
title: "ISymUnmanagedReader::GetSymbolStoreFileName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymbolStoreFileName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 951dfd45f6b313b6cde28f3f65f2799380a33a78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="5bcbf-102">ISymUnmanagedReader::GetSymbolStoreFileName 메서드</span><span class="sxs-lookup"><span data-stu-id="5bcbf-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="5bcbf-103">기호 저장소의 디스크에 파일 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcbf-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bcbf-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bcbf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bcbf-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5bcbf-106">[in] 크기는 `szName` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcbf-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5bcbf-107">[out] 반환 되는 이름 길이 받는 변수에 대 한 포인터 `szName`, null 종결을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bcbf-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="5bcbf-108">[out] 기호 저장소의 파일 이름을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcbf-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bcbf-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5bcbf-109">Return Value</span></span>  
 <span data-ttu-id="5bcbf-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5bcbf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcbf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bcbf-111">Requirements</span></span>  
 <span data-ttu-id="5bcbf-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5bcbf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcbf-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bcbf-113">See Also</span></span>  
 [<span data-ttu-id="5bcbf-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bcbf-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
