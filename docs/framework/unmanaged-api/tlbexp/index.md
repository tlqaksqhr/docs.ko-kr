---
title: Tlbexp 도우미 함수(관리되지 않는 API 참조)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a9d483e101fdb94a43055b6081fcc31a458a1ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="be713-102">Tlbexp 도우미 함수(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="be713-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="be713-103">[형식 라이브러리 내보내기 도구](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) TlbRef.dll 라는 동적 연결 라이브러리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="be713-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="be713-104">이 DLL 두 도우미 함수 및 어셈블리를 형식 라이브러리로 변환 하는 동안 내보내기 도구를 사용 하는 인터페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="be713-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be713-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="be713-105">In This Section</span></span>  
 [<span data-ttu-id="be713-106">GetTypeLibInfo 함수</span><span class="sxs-lookup"><span data-stu-id="be713-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="be713-107">형식 라이브러리에 대 한 지역화 및 운영 체제 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be713-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="be713-108">LoadTypeLibWithResolver 함수</span><span class="sxs-lookup"><span data-stu-id="be713-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="be713-109">구현을 사용 하 여 형식 라이브러리를 로드는 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 해결 하려면 형식 라이브러리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="be713-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="be713-110">ITypeLibResolver 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be713-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="be713-111">제공 된 [ResolveTypeLib 메서드](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), 형식 라이브러리의 정규화 된 경로 반환 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="be713-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
