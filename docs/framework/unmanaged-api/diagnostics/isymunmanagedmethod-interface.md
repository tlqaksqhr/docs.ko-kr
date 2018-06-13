---
title: ISymUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427433"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="ca237-102">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca237-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="ca237-103">기호 저장소 내의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="ca237-104">이 인터페이스는만 형식 관련 특성 대신 메서드의 기호 관련 특성에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca237-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-105">Methods</span></span>  
  
|<span data-ttu-id="ca237-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-106">Method</span></span>|<span data-ttu-id="ca237-107">설명</span><span class="sxs-lookup"><span data-stu-id="ca237-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca237-108">GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="ca237-109">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="ca237-110">GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="ca237-111">문서 내에서 지정된 된 위치에 해당 하는이 메서드 내에서 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="ca237-112">GetParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="ca237-113">이 메서드에 대 한 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="ca237-114">GetRanges 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="ca237-115">제공 되는 위치가 문서에는 위치가이 메서드에 설명 되어 있는 Microsoft intermediate language (MSIL)의 범위에 해당 하는 시작 및 종료 오프셋된 쌍의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="ca237-116">GetRootScope 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="ca237-117">이 메서드 내에서 루트 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="ca237-118">이 범위는 전체 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="ca237-119">GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="ca237-120">지정된 된 오프셋을 포함 하는이 메서드 내에서 최대 포함 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="ca237-121">GetSequencePointCount 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="ca237-122">이 메서드 내에서 시퀀스 위치 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="ca237-123">GetSequencePoints 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="ca237-124">이 메서드 내에서 모든 시퀀스 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="ca237-125">GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="ca237-126">이 방법의 원본에 대 한 시작 및 끝 문서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="ca237-127">GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="ca237-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="ca237-128">이 메서드에 대 한 메타 데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ca237-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca237-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca237-129">Requirements</span></span>  
 <span data-ttu-id="ca237-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca237-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca237-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca237-131">See Also</span></span>  
 [<span data-ttu-id="ca237-132">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca237-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
