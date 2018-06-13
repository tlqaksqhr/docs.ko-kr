---
title: ICorDebugMergedAssemblyRecord::GetSimpleName 메서드
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c5499b63e5201fbf42ece07f4f3eff52129e09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417494"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="98b99-102">ICorDebugMergedAssemblyRecord::GetSimpleName 메서드</span><span class="sxs-lookup"><span data-stu-id="98b99-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="98b99-103">어셈블리의 단순한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b99-104">구문</span><span class="sxs-lookup"><span data-stu-id="98b99-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98b99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98b99-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="98b99-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="98b99-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="98b99-108">문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98b99-109">설명</span><span class="sxs-lookup"><span data-stu-id="98b99-109">Remarks</span></span>  
 <span data-ttu-id="98b99-110">이 메서드는 파일 확장명, 버전, 문화권 또는 공개 키 토큰 없이 어셈블리의 단순한 이름(예: "System.Collections")을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="98b99-111">관리 코드의 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98b99-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98b99-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98b99-113">Requirements</span></span>  
 <span data-ttu-id="98b99-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98b99-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98b99-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98b99-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98b99-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98b99-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98b99-117">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98b99-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b99-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98b99-118">See Also</span></span>  
 [<span data-ttu-id="98b99-119">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98b99-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="98b99-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98b99-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
