---
title: CorAssemblyFlags 열거형
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6ec37bbd8750c27a41b5f18180c7726cdcd483
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442841"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="d9fd0-102">CorAssemblyFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="d9fd0-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="d9fd0-103">어셈블리 컴파일에 적용되는 메타데이터를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fd0-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9fd0-104">Syntax</span></span>  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d9fd0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d9fd0-105">Members</span></span>  
  
|<span data-ttu-id="d9fd0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d9fd0-106">Member</span></span>|<span data-ttu-id="d9fd0-107">설명</span><span class="sxs-lookup"><span data-stu-id="d9fd0-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="d9fd0-108">어셈블리 참조는 전체, 해시 되지 않은 공개 키 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="d9fd0-109">프로세서 아키텍처 지정 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="d9fd0-110">프로세서 아키텍처 중립 임을 나타냅니다 (PE32).</span><span class="sxs-lookup"><span data-stu-id="d9fd0-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="d9fd0-111">프로세서 아키텍처 x86 (PE32) 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="d9fd0-112">프로세서 아키텍처 Itanium (PE32 +) 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="d9fd0-113">프로세서 아키텍처 AMD X64 (PE32 +) 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="d9fd0-114">프로세서 아키텍처 ARM (PE32) 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="d9fd0-115">어셈블리가 참조 어셈블리; 임을 나타냅니다. 즉, 모든 아키텍처에 적용 되지만 모든 아키텍처에서 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="d9fd0-116">따라서 플래그는 동일 `afPA_Mask`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="d9fd0-117">프로세서 아키텍처 플래그에 전파 해야 있는지 나타냅니다는 `AssemblyRef` 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="d9fd0-118">프로세서 아키텍처를 설명 하는 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="d9fd0-119">프로세서 아키텍처 설명을 포함 되어 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="d9fd0-120">프로세서 아키텍처 플래그 인덱스에서 시프트 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="d9fd0-121">해당 값을 나타냅니다는 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> 의 <xref:System.Diagnostics.DebuggableAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="d9fd0-122">해당 값을 나타냅니다는 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> 의 <xref:System.Diagnostics.DebuggableAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="d9fd0-123">어셈블리가 다른 게시자의 어셈블리에 실행 시 대상이 될 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="d9fd0-124">콘텐츠 형식을 설명 하는 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="d9fd0-125">기본 콘텐츠 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="d9fd0-126">나타냅니다는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9fd0-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9fd0-127">Requirements</span></span>  
 <span data-ttu-id="d9fd0-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9fd0-129">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d9fd0-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d9fd0-130">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9fd0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fd0-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9fd0-131">See Also</span></span>  
 [<span data-ttu-id="d9fd0-132">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="d9fd0-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
