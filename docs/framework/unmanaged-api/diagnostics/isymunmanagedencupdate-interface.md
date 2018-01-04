---
title: "ISymUnmanagedENCUpdate 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate
helpviewer_keywords: ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f68d000824779fcffb90ec031b86b50e8c80eccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="6f5a0-102">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f5a0-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="6f5a0-103">편집 하며 계속 하기 기능에 대 한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f5a0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-104">Methods</span></span>  
  
|<span data-ttu-id="6f5a0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-105">Method</span></span>|<span data-ttu-id="6f5a0-106">설명</span><span class="sxs-lookup"><span data-stu-id="6f5a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f5a0-107">GetLocalVariableCount 메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="6f5a0-108">지역 변수의 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="6f5a0-109">GetLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="6f5a0-110">지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="6f5a0-111">InitializeForEnc 메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="6f5a0-112">처음 호출 하기 전에 계산 해야 메서드 경계 수는 [isymunmanagedencupdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="6f5a0-113">UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="6f5a0-114">다시 컴파일되지 않은, 하지만 해당 줄 독립적으로 이동 하는 방법에 대 한 줄 정보를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="6f5a0-115">각 문에 대 한 델타 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="6f5a0-116">UpdateSymbolStore2 메서드</span><span class="sxs-lookup"><span data-stu-id="6f5a0-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="6f5a0-117">컴파일러가 줄 정보 요구 사항을 충족 하는 프로그램 데이터베이스 (PDB) 스트립에서 수정 되지 않은 함수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="6f5a0-118">오래 된 PDB 줄 정보 및 모든 줄은 함수에 대 한 델타 올바른 줄 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5a0-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f5a0-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f5a0-119">Requirements</span></span>  
 <span data-ttu-id="6f5a0-120">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6f5a0-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5a0-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f5a0-121">See Also</span></span>  
 [<span data-ttu-id="6f5a0-122">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f5a0-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
