---
title: CorElementType Enumeration1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorElementType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorElementType
helpviewer_keywords: CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8932e295aa1a6c6cf961e7b3a218e76984da02cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="8435f-102">CorElementType Enumeration1</span><span class="sxs-lookup"><span data-stu-id="8435f-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="8435f-103">공용 언어 런타임에서 지정 <xref:System.Type>, 형식 한정자 또는 형식 메타 데이터 서명에 형식에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8435f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8435f-104">Syntax</span></span>  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a><span data-ttu-id="8435f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8435f-105">Members</span></span>  
  
|<span data-ttu-id="8435f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8435f-106">Member</span></span>|<span data-ttu-id="8435f-107">설명</span><span class="sxs-lookup"><span data-stu-id="8435f-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="8435f-108">내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="8435f-109">Void 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="8435f-110">Boolean 형식</span><span class="sxs-lookup"><span data-stu-id="8435f-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="8435f-111">문자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="8435f-112">부호 있는 1 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="8435f-113">부호 없는 1바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="8435f-114">부호 있는 2 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="8435f-115">부호 없는 2 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="8435f-116">부호 있는 4 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="8435f-117">부호 없는 4 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="8435f-118">부호 있는 8 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="8435f-119">부호 없는 8 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="8435f-120">4 바이트 부동 소수점입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="8435f-121">8 바이트 부동 소수점입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="8435f-122">System.String 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="8435f-123">포인터 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="8435f-124">참조 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="8435f-125">값 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="8435f-126">클래스 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="8435f-127">클래스 변수 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="8435f-128">다차원 배열 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="8435f-129">제네릭 형식에 대 한 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="8435f-130">형식화된 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="8435f-131">기본 정수 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="8435f-132">부호 없는 원시 정수 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="8435f-133">함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="8435f-134">System.Object 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="8435f-135">단일 차원, 0 인 배열 형식 한정자</span><span class="sxs-lookup"><span data-stu-id="8435f-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="8435f-136">메서드 변수 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="8435f-137">C 언어는 필수 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="8435f-138">C 언어의 선택적 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="8435f-139">내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="8435f-140">잘못된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="8435f-141">내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="8435f-142">형식 한정자가 가변 개수의 매개 변수 목록에 대 한 센티널입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="8435f-143">내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8435f-144">설명</span><span class="sxs-lookup"><span data-stu-id="8435f-144">Remarks</span></span>  
 <span data-ttu-id="8435f-145">형식 한정자는 더 복잡 한 형식을 나타내는 대 한 기초를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="8435f-146">A `CorElementType` 형식 한정자 값 바로 뒤에 오는 형식 서명에 하는 값에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="8435f-147">다음에 나오는 값의 `CorElementType` 형식 한정자 값이 될 수 있습니다는 `CorElementType` 단순 유형 값, 메타 데이터 토큰 또는 다음 테이블에 지정 된 다른 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8435f-148">모든 숫자 (*번호*, *인수 개수*, *메타 데이터 토큰*, *순위*, *count*, 및 *바인딩된*) 압축 된 정수로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="8435f-149">참조 [Standard ecma-335-인프라 CLI (공용 언어)](http://go.microsoft.com/fwlink/?LinkID=116487) 자세한 내용은 ECMA 웹 사이트에서.</span><span class="sxs-lookup"><span data-stu-id="8435f-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="8435f-150">형식 한정자</span><span class="sxs-lookup"><span data-stu-id="8435f-150">Type modifier</span></span>|<span data-ttu-id="8435f-151">형식</span><span class="sxs-lookup"><span data-stu-id="8435f-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="8435f-152">ELEMENT_TYPE_PTR <는 `CorElementType` 값 ></span><span class="sxs-lookup"><span data-stu-id="8435f-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="8435f-153">ELEMENT_TYPE_BYREF <는 `CorElementType` 값 ></span><span class="sxs-lookup"><span data-stu-id="8435f-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="8435f-154">ELEMENT_TYPE_VALUETYPE <는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="8435f-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="8435f-155">ELEMENT_TYPE_CLASS <는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="8435f-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="8435f-156">ELEMENT_TYPE_VAR \<번호 ></span><span class="sxs-lookup"><span data-stu-id="8435f-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="8435f-157">ELEMENT_TYPE_ARRAY <는 `CorElementType` 값 > \<순위 > \<count1 > \<bound1 >... \<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="8435f-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="8435f-158">ELEMENT_TYPE_GENERICINST <는 `mdTypeDef` 메타 데이터 토큰 > \<인수 개수 > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="8435f-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="8435f-159">ELEMENT_TYPE_FNPTR \<호출 규칙을 포함 하는 함수에 대 한 전체 시그니처 ></span><span class="sxs-lookup"><span data-stu-id="8435f-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="8435f-160">ELEMENT_TYPE_SZARRAY <는 `CorElementType` 값 ></span><span class="sxs-lookup"><span data-stu-id="8435f-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="8435f-161">ELEMENT_TYPE_MVAR \<번호 ></span><span class="sxs-lookup"><span data-stu-id="8435f-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="8435f-162">ELEMENT_TYPE_ <는 `mdTypeRef` 또는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="8435f-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="8435f-163">E_T_CMOD_OPT <는 `mdTypeRef` 또는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="8435f-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8435f-164">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8435f-164">Requirements</span></span>  
 <span data-ttu-id="8435f-165">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8435f-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8435f-166">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8435f-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8435f-167">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8435f-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8435f-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8435f-168">See Also</span></span>  
 [<span data-ttu-id="8435f-169">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8435f-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
