---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 메서드
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9082a05900330be27066b64f2ad0e99b87e04c61
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="b3d5d-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 메서드</span><span class="sxs-lookup"><span data-stu-id="b3d5d-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="b3d5d-103">컴파일러가 줄 정보 요구 사항을 충족 하는 제공 된 프로그램 데이터베이스 (PDB) 스트림, 수정 되지 않은 함수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d5d-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="b3d5d-104">오래 된 PDB 줄 정보 및 모든 줄은 함수에 대 한 델타 올바른 줄 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d5d-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3d5d-105">구문</span><span class="sxs-lookup"><span data-stu-id="b3d5d-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3d5d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3d5d-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="b3d5d-107">[in] 에 대 한 포인터는 [IStream](https://msdn.microsoft.com/library/aa380034.aspx) 줄 정보가 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d5d-107">[in] A pointer to an [IStream](https://msdn.microsoft.com/library/aa380034.aspx) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="b3d5d-108">[in] 에 대 한 포인터는 [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) 변경 된 줄이 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d5d-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="b3d5d-109">[in] A `ULONG` 변경 된 줄 수를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d5d-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3d5d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3d5d-110">Return Value</span></span>  
 <span data-ttu-id="b3d5d-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b3d5d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3d5d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3d5d-112">Requirements</span></span>  
 <span data-ttu-id="b3d5d-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b3d5d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d5d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3d5d-114">See Also</span></span>  
 [<span data-ttu-id="b3d5d-115">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3d5d-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
