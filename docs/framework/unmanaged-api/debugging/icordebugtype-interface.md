---
title: ICorDebugType Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de2871b406bb9da84d20d7c526ad4a703baae409
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422873"
---
# <a name="icordebugtype-interface1"></a><span data-ttu-id="f450a-102">ICorDebugType Interface1</span><span class="sxs-lookup"><span data-stu-id="f450a-102">ICorDebugType Interface1</span></span>
<span data-ttu-id="f450a-103">형식을, 기본 또는 복합 (즉, 사용자 정의)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="f450a-104">형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f450a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-105">Methods</span></span>  
  
|<span data-ttu-id="f450a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-106">Method</span></span>|<span data-ttu-id="f450a-107">설명</span><span class="sxs-lookup"><span data-stu-id="f450a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f450a-108">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="f450a-109">제네릭 참조 하는 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다 <xref:System.Type> 이 참조 하는 클래스의 매개 변수 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="f450a-110">GetBase 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="f450a-111">한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 이 참조 하는 클래스의 기본 클래스를 참조 하는 `ICorDebugType`있는 경우.</span><span class="sxs-lookup"><span data-stu-id="f450a-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="f450a-112">GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="f450a-113">이 형식의 생성자를 참조 하는 ICorDebugClass에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="f450a-114">GetFirstTypeParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="f450a-115">한 인터페이스 포인터를 가져옵니다는 `ICorDebugType` 첫 번째 제네릭을 참조 하는 <xref:System.Type> 이 참조 하는 클래스의 생성자에 대 한 매개 변수 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="f450a-116">GetRank 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="f450a-117">배열 형식에서 차원 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="f450a-118">GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="f450a-119">토큰을 지정 된 스택 프레임에 지정 된 필드에서 참조 하는 정적 필드의 값이 포함 된 ICorDebugValue에 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="f450a-120">GetType 메서드</span><span class="sxs-lookup"><span data-stu-id="f450a-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="f450a-121">공용 언어 런타임의 네이티브 형식을 설명 하는 CorElementType 값을 가져옵니다 <xref:System.Type> 받았습니다 참조 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f450a-122">설명</span><span class="sxs-lookup"><span data-stu-id="f450a-122">Remarks</span></span>  
 <span data-ttu-id="f450a-123">형식이 제네릭인 경우 `ICorDebugClass` 는 인스턴스화되지 않은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="f450a-124">`ICorDebugType` 인터페이스는 인스턴스화된 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="f450a-125">예를 들어 Hashtable\<K, V >을 표시 `ICorDebugClass`반면, 해시 테이블\<Int32, String >을 표시 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="f450a-126">제네릭이 아닌 형식은 둘 다로 표현 됩니다 `ICorDebugClass` 및 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="f450a-127">두 번째 인터페이스 형식 인스턴스화 처리 하는.NET Framework 버전 2.0에서에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f450a-128">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f450a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f450a-129">Requirements</span></span>  
 <span data-ttu-id="f450a-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f450a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f450a-131">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f450a-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f450a-132">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f450a-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f450a-133">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f450a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f450a-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f450a-134">See Also</span></span>  
 [<span data-ttu-id="f450a-135">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f450a-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
