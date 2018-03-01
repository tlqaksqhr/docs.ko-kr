---
title: "CorMethodAttr 열거형"
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
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e144b64664a149115f3047b98267c2f218a76e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="31dd2-102">CorMethodAttr 열거형</span><span class="sxs-lookup"><span data-stu-id="31dd2-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="31dd2-103">메서드의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31dd2-104">구문</span><span class="sxs-lookup"><span data-stu-id="31dd2-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="31dd2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="31dd2-105">Members</span></span>  
  
|<span data-ttu-id="31dd2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="31dd2-106">Member</span></span>|<span data-ttu-id="31dd2-107">설명</span><span class="sxs-lookup"><span data-stu-id="31dd2-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="31dd2-108">멤버 액세스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="31dd2-109">멤버를 참조할 수 없음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="31dd2-110">멤버를 부모 형식에 의해서만 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="31dd2-111">멤버에만이 어셈블리의에서 하위 형식에서 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="31dd2-112">멤버는 어셈블리의 다른 사용자가 액세스할 수 있습니다 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="31dd2-113">멤버 유형 및 하위 유형 에서만 액세스할 수 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="31dd2-114">어셈블리의 다른 형식 및 파생된 클래스에서 액세스할 수 있는 멤버 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="31dd2-115">멤버를 범위에 액세스할 수 있는 모든 형식에서 액세스할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="31dd2-116">인스턴스 멤버 아니라 형식의 일부로 멤버 정의 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="31dd2-117">메서드를 재정의할 수 없음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="31dd2-118">메서드를 재정의할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="31dd2-119">메서드 이름 대신 방금 이름과 시그니처를 여는 숨깁니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="31dd2-120">가상 테이블 레이아웃을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="31dd2-121">가상 테이블에서이 메서드에 대 한 사용 되는 슬롯 다시 사용할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="31dd2-122">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="31dd2-123">메서드가 가상 테이블에서 새 슬롯을 항상 가져오도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="31dd2-124">가 표시 되는 동일한 형식에서 메서드를 재정의할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="31dd2-125">메서드가 구현 되지 않았음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="31dd2-126">메서드가 특수 문자이 고 해당 이름을 설명 하 고 있음을 지정 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="31dd2-127">메서드 구현 PInvoke를 사용 하 여 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="31dd2-128">비관리 코드로 내보낼 관리 되는 메서드는 메서드가 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="31dd2-129">공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="31dd2-130">공용 언어 런타임 메서드 이름의 인코딩을 확인 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="31dd2-131">메서드가 연결 된 보안 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="31dd2-132">메서드가 보안 코드를 포함 하는 다른 메서드를 호출을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31dd2-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31dd2-133">Requirements</span></span>  
 <span data-ttu-id="31dd2-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="31dd2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31dd2-135">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="31dd2-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="31dd2-136">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31dd2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31dd2-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31dd2-137">See Also</span></span>  
 [<span data-ttu-id="31dd2-138">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="31dd2-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
