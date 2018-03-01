---
title: "ICorDebugModule2::ApplyChanges 메서드"
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
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4855b7a42d471304d000465a0437f29bdff05494
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="e02eb-102">ICorDebugModule2::ApplyChanges 메서드</span><span class="sxs-lookup"><span data-stu-id="e02eb-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="e02eb-103">실행 중인 프로세스에 메타 데이터의 변경 내용과 Microsoft MSIL (intermediate language) 코드의 변경 내용을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e02eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="e02eb-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e02eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e02eb-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="e02eb-106">[in] 델타 메타 데이터를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="e02eb-107">[in] 델타 메타 데이터가 들어 있는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="e02eb-108">버퍼의 주소에서 반환 되는 [imetadataemit2:: Savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e02eb-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="e02eb-109">메타 데이터에 상대 가상 주소 (Rva)는 MSIL 코드의 시작을 기준으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="e02eb-110">[in] MSIL 코드 델타를 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="e02eb-111">[in] 업데이트 된 MSIL 코드를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e02eb-112">설명</span><span class="sxs-lookup"><span data-stu-id="e02eb-112">Remarks</span></span>  
 <span data-ttu-id="e02eb-113">`pbMetadata` 특수 델타 메타 데이터 형식으로 매개 변수는 (으로 출력 하 여 [imetadataemit2:: Savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="e02eb-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="e02eb-114">`pbMetadata`이전 메타 데이터를 기반으로 하 고 해당 자료에 적용 하려면 개별 변경 내용을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="e02eb-115">반면,는 `pbIL[`] 매개 변수는 새 업데이트 방법이 MSIL 포함 해당 메서드에 대 한 이전 MSIL을 완전히 대체 것 이며</span><span class="sxs-lookup"><span data-stu-id="e02eb-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="e02eb-116">디버거를 호출 하는 메모리에서 델타 MSIL 및 메타 데이터 생성 되 면 `ApplyChanges` 공용 언어 런타임 (CLR)로 변경 내용을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="e02eb-117">메뉴 및 도구 모음을 런타임에 해당 메타 데이터 테이블 업데이트는 프로세스에 저장 하 고 새 MSIL 새 MSIL 적시에 (JIT) 컴파일 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="e02eb-118">디버거를 호출 해야 변경 내용이 적용 된 경우 [imetadataemit2:: Resetenclog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) 다음 편집 세션에 대 한 준비를 합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="e02eb-119">디버거 다음 프로세스를 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="e02eb-120">디버거 호출할 때마다 `ApplyChanges` 델타 메타 데이터가 포함 모듈에서 호출 또한 해야 [imetadataemit:: Applyeditandcontinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) 모든 복사본을 제외한 해당 모듈의 메타 데이터의 해당 복사본에 같은 델타 메타 데이터와 변경 내용을 생성 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="e02eb-121">메타 데이터의 복사본을 어떻게 하 든 되 면 동기화를-실제 메타 데이터와 수 항상 해당 복사본 버리는 디버거와 새 복사본을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="e02eb-122">경우는 `ApplyChanges` 메서드가 실패 하면 디버그 세션이 유효 하지 않은 상태 이므로 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e02eb-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e02eb-123">Requirements</span></span>  
 <span data-ttu-id="e02eb-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e02eb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e02eb-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e02eb-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e02eb-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e02eb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e02eb-127">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e02eb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
