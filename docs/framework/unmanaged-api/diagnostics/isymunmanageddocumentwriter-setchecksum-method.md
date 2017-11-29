---
title: "ISymUnmanagedDocumentWriter::SetCheckSum 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9693b21c2b3819096ec4aeb0a275fccf76307de0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="66330-102">ISymUnmanagedDocumentWriter::SetCheckSum 메서드</span><span class="sxs-lookup"><span data-stu-id="66330-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="66330-103">체크섬 정보를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66330-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66330-104">구문</span><span class="sxs-lookup"><span data-stu-id="66330-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66330-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66330-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="66330-106">[in] 알고리즘 식별자를 나타내는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="66330-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="66330-107">[in] A `ULONG32` 의 크기를 바이트 단위로 나타내는 `checkSum` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="66330-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="66330-108">[in] 체크섬 정보를 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="66330-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66330-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="66330-109">Return Value</span></span>  
 <span data-ttu-id="66330-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="66330-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66330-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66330-111">Requirements</span></span>  
 <span data-ttu-id="66330-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="66330-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66330-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66330-113">See Also</span></span>  
 [<span data-ttu-id="66330-114">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66330-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
