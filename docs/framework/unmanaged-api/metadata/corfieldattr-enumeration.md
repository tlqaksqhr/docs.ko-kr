---
title: "CorFieldAttr 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5128ea59f7668737885835723156fc7f1786872
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="9ab23-102">CorFieldAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="9ab23-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="9ab23-103">필드에 대한 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab23-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ab23-104">Syntax</span></span>  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9ab23-105">멤버</span><span class="sxs-lookup"><span data-stu-id="9ab23-105">Members</span></span>  
  
|<span data-ttu-id="9ab23-106">멤버</span><span class="sxs-lookup"><span data-stu-id="9ab23-106">Member</span></span>|<span data-ttu-id="9ab23-107">설명</span><span class="sxs-lookup"><span data-stu-id="9ab23-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="9ab23-108">내게 필요한 옵션 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="9ab23-109">필드는 참조할 수 없음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="9ab23-110">필드 부모 형식의 액세스할 수 있게 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="9ab23-111">필드에 해당 어셈블리의 파생된 클래스에서 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="9ab23-112">필드에 해당 어셈블리의 모든 형식에서 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="9ab23-113">필드가 해당 형식을 액세스할 수 있게 되며 파생 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="9ab23-114">어셈블리의 모든 형식 및 파생된 클래스에서 액세스할 수 있는 필드 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="9ab23-115">필드에이 범위의 표시 유형이 적용 된 모든 형식에서 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="9ab23-116">필드가 해당 형식의 멤버가 아닌 인스턴스 멤버 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="9ab23-117">초기화 한 후 필드를 변경할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="9ab23-118">필드 값은 컴파일 타임 상수 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="9ab23-119">해당 유형이 원격으로 연결할 때는 필드가 serialize 되지 않음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="9ab23-120">필드가 특수 문자이 고 해당 이름을 설명 하 고 있음을 지정 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="9ab23-121">필드 구현은 PInvoke를 통해 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="9ab23-122">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="9ab23-123">공용 언어 런타임 메타 데이터 내부 Api 확인 하도록 지정 합니다 이름의 인코딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="9ab23-124">필드에 마샬링 정보가 포함 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="9ab23-125">필드 기본값을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="9ab23-126">필드의 상대 가상 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ab23-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ab23-127">Requirements</span></span>  
 <span data-ttu-id="9ab23-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ab23-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ab23-129">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9ab23-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9ab23-130">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ab23-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab23-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ab23-131">See Also</span></span>  
 [<span data-ttu-id="9ab23-132">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="9ab23-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
