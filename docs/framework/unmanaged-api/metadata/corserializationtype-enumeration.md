---
title: "CorSerializationType 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSerializationType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSerializationType
helpviewer_keywords: CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f6650298364f7deb60d553ee21f5028f5cbe7400
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="96048-102">CorSerializationType 열거형</span><span class="sxs-lookup"><span data-stu-id="96048-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="96048-103">공용 언어 런타임에서 개체가 serialize 되는 방식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96048-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96048-104">구문</span><span class="sxs-lookup"><span data-stu-id="96048-104">Syntax</span></span>  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="96048-105">멤버</span><span class="sxs-lookup"><span data-stu-id="96048-105">Members</span></span>  
  
|<span data-ttu-id="96048-106">멤버</span><span class="sxs-lookup"><span data-stu-id="96048-106">Member</span></span>|<span data-ttu-id="96048-107">설명</span><span class="sxs-lookup"><span data-stu-id="96048-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="96048-108">개체의 serialization 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96048-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="96048-109">Boolean 형식의 개체를 serialize</span><span class="sxs-lookup"><span data-stu-id="96048-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="96048-110">개체가 문자 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="96048-111">부호 있는 1 바이트 정수로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="96048-112">부호 없는 1 바이트 정수로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="96048-113">부호 있는 2 바이트 정수 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="96048-114">부호 없는 2 바이트 정수인 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="96048-115">부호 있는 4 바이트 정수로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="96048-116">부호 없는 4 바이트 정수로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="96048-117">부호 있는 8 바이트 정수 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="96048-118">부호 없는 8 바이트 정수로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="96048-119">4 바이트 부동 소수점으로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="96048-120">8 바이트 부동 소수점으로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="96048-121">개체가는 System.String 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="96048-122">단일 차원, 개체를 serialize 0 인 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="96048-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="96048-123">개체가 제네릭 형식으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="96048-124">개체가는 태그가 지정 된 개체로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="96048-125">개체가 필드로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="96048-126">개체가 속성으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="96048-127">열거형으로 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96048-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96048-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96048-128">Requirements</span></span>  
 <span data-ttu-id="96048-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96048-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96048-130">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="96048-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="96048-131">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96048-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96048-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96048-132">See Also</span></span>  
 [<span data-ttu-id="96048-133">메타 데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="96048-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
