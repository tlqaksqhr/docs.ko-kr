---
title: "ISymUnmanagedReader 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader
helpviewer_keywords: ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56e0012ae1412c0fb5b434d3b4c0221831296c60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="ae4c5-102">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae4c5-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="ae4c5-103">문서, 메서드 및 기호 저장소 내의 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae4c5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-104">Methods</span></span>  
  
|<span data-ttu-id="ae4c5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-105">Method</span></span>|<span data-ttu-id="ae4c5-106">설명</span><span class="sxs-lookup"><span data-stu-id="ae4c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae4c5-107">GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="ae4c5-108">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-108">Finds a document.</span></span>|  
|[<span data-ttu-id="ae4c5-109">GetDocuments 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="ae4c5-110">기호 저장소에 정의 된 모든 문서의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="ae4c5-111">GetDocumentVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="ae4c5-112">지정 된 문서의 지정된 된 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="ae4c5-113">GetGlobalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="ae4c5-114">모든 전역 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="ae4c5-115">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="ae4c5-116">메서드 토큰이 지정 된 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="ae4c5-117">GetMethodByVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="ae4c5-118">메서드 토큰 및 편집 복사 버전 번호를 지정 된 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="ae4c5-119">GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="ae4c5-120">문서에서 지정된 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="ae4c5-121">GetMethodsFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="ae4c5-122">문서에서 지정된 된 위치에 중단점을 포함 하며 각 방법의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="ae4c5-123">GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="ae4c5-124">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="ae4c5-125">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="ae4c5-126">이 기호 저장소 내의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="ae4c5-127">GetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="ae4c5-128">이름을 기반으로 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="ae4c5-129">GetSymbolStoreFileName 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="ae4c5-130">기호 저장소의 디스크에 파일 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="ae4c5-131">GetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="ae4c5-132">있는 경우 모듈의 사용자 진입점으로 지정 된 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="ae4c5-133">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="ae4c5-134">지정 된 부모 및 이름을 로컬이 아닌 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="ae4c5-135">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="ae4c5-136">이 판독기가 되는 모듈의 파일 이름과 함께 연결 된 메타 데이터 가져오기 인터페이스의 기호 판독기를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="ae4c5-137">ReplaceSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="ae4c5-138">기존 기호 저장소를 델타 기호 저장소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="ae4c5-139">UpdateSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="ae4c5-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="ae4c5-140">기존 기호 저장소를 델타 기호 저장소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae4c5-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae4c5-141">Requirements</span></span>  
 <span data-ttu-id="ae4c5-142">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ae4c5-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4c5-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae4c5-143">See Also</span></span>  
 [<span data-ttu-id="ae4c5-144">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae4c5-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="ae4c5-145">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae4c5-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
