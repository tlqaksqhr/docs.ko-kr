---
title: ISymUnmanagedVariable 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3db4fc691637c049e0374416cb92a2056555ad11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428702"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="05ff8-102">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05ff8-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="05ff8-103">매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05ff8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-104">Methods</span></span>  
  
|<span data-ttu-id="05ff8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-105">Method</span></span>|<span data-ttu-id="05ff8-106">설명</span><span class="sxs-lookup"><span data-stu-id="05ff8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05ff8-107">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="05ff8-108">이 변수에 대 한 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="05ff8-109">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="05ff8-110">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="05ff8-111">이 변수에 대 한 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="05ff8-112">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="05ff8-113">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="05ff8-114">이 변수에 대 한 세 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="05ff8-115">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="05ff8-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="05ff8-117">이 변수의 주소가의 종류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="05ff8-118">GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="05ff8-119">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="05ff8-120">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="05ff8-121">해당 부모 노드에이 변수의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="05ff8-122">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="05ff8-123">이 변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="05ff8-124">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="05ff8-125">이 변수 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="05ff8-126">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="05ff8-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="05ff8-127">해당 부모 노드에이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ff8-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05ff8-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05ff8-128">Requirements</span></span>  
 <span data-ttu-id="05ff8-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="05ff8-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ff8-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05ff8-130">See Also</span></span>  
 [<span data-ttu-id="05ff8-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05ff8-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
