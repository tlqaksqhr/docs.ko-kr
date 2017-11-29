---
title: "ICorProfilerInfo::GetILFunctionBody 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6908b6c765a56ef0aa43a66cc58ec74b525bc2d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="ef6e8-102">ICorProfilerInfo::GetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="ef6e8-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="ef6e8-103">헤더에서 시작 되는 Microsoft MSIL (intermediate language) 코드에서 메서드 본문에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef6e8-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef6e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef6e8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ef6e8-106">[in] 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="ef6e8-107">[in] 메서드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="ef6e8-108">[out] 메서드 헤더에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="ef6e8-109">[out] 크기의 메서드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef6e8-110">설명</span><span class="sxs-lookup"><span data-stu-id="ef6e8-110">Remarks</span></span>  
 <span data-ttu-id="ef6e8-111">메서드는 현재 모듈에 의해 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="ef6e8-112">때문에 `GetILFunctionBody` 메서드 전에 공용 언어 런타임 (CLR)에서 로드 된 MSIL 코드에 대 한 도구 액세스를 제공 하도록 설계 되었습니다, 메서드의 메타 데이터 토큰을 사용 하 여 원하는 인스턴스를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="ef6e8-113">`GetILFunctionBody`경우에 CORPROF_E_FUNCTION_NOT_IL HRESULT를 반환할 수 있습니다는 `methodId` 모든 MSIL 코드 (추상 메서드 또는 플랫폼 호출 (PInvoke) 메서드 같은) 없이 메서드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef6e8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef6e8-114">Requirements</span></span>  
 <span data-ttu-id="ef6e8-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef6e8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6e8-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef6e8-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef6e8-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef6e8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef6e8-118">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6e8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6e8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef6e8-119">See Also</span></span>  
 [<span data-ttu-id="ef6e8-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef6e8-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
