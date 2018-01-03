---
title: "디버깅 전역 정적 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7fde0941959619f4832019806401be0ffddb81e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-global-static-functions"></a><span data-ttu-id="2293d-102">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="2293d-102">Debugging Global Static Functions</span></span>
<span data-ttu-id="2293d-103">이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 전역 정적 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-103">This section describes the unmanaged global static functions that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2293d-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2293d-104">In This Section</span></span>  
 [<span data-ttu-id="2293d-105">_EFN_GetManagedExcepStack 함수</span><span class="sxs-lookup"><span data-stu-id="2293d-105">_EFN_GetManagedExcepStack Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 <span data-ttu-id="2293d-106">관리되는 예외 개체 주소를 제공하면 내부에 포함된 스택 추적의 문자열 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-106">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
 [<span data-ttu-id="2293d-107">_EFN_GetManagedObjectFieldInfo 함수</span><span class="sxs-lookup"><span data-stu-id="2293d-107">_EFN_GetManagedObjectFieldInfo Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 <span data-ttu-id="2293d-108">제공된 개체 포인터와 필드 이름을 사용하여 개체 시작부터 필드 및 필드 값까지의 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-108">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
 [<span data-ttu-id="2293d-109">_EFN_GetManagedObjectName 함수</span><span class="sxs-lookup"><span data-stu-id="2293d-109">_EFN_GetManagedObjectName Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 <span data-ttu-id="2293d-110">제공된 관리되는 개체 포인터를 사용하여 형식 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-110">Gets the name of a type by using the provided managed object pointer.</span></span>  
  
 [<span data-ttu-id="2293d-111">_EFN_StackTrace 함수</span><span class="sxs-lookup"><span data-stu-id="2293d-111">_EFN_StackTrace Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 <span data-ttu-id="2293d-112">비관리 코드와 관리 코드 간 각 전환에 대해 하나씩, `CONTEXT` 레코드 배열 및 관리되는 스택 추적의 텍스트 표시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-112">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
 [<span data-ttu-id="2293d-113">CLRDataCreateInstance 함수</span><span class="sxs-lookup"><span data-stu-id="2293d-113">CLRDataCreateInstance Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 <span data-ttu-id="2293d-114">지정된 대상 프로세스에 대한 지정된 인터페이스 개체를 만들려고 CLR(공용 언어 런타임) 데이터 액세스 서비스에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-114">Called by the common language runtime (CLR) data access services to create the specified interface object for the specified target process.</span></span>  
  
 [<span data-ttu-id="2293d-115">PFN_CLRDataCreateInstance 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="2293d-115">PFN_CLRDataCreateInstance Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 <span data-ttu-id="2293d-116">지정된 대상 프로세스에 대한 지정된 인터페이스 개체를 만들려고 CLR 데이터 액세스 서비스에 의해 호출되는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="2293d-116">Points to a function that is called by the CLR data access services to create the specified interface object for the specified target process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2293d-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2293d-117">Related Sections</span></span>  
 [<span data-ttu-id="2293d-118">디버깅 Coclass</span><span class="sxs-lookup"><span data-stu-id="2293d-118">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="2293d-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2293d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="2293d-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="2293d-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="2293d-121">디버깅 구조체</span><span class="sxs-lookup"><span data-stu-id="2293d-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
