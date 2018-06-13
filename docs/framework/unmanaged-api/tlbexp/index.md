---
title: Tlbexp 도우미 함수(관리되지 않는 API 참조)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455875"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="0f6bd-102">Tlbexp 도우미 함수(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="0f6bd-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="0f6bd-103">[형식 라이브러리 내보내기 도구](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) TlbRef.dll 라는 동적 연결 라이브러리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6bd-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="0f6bd-104">이 DLL 두 도우미 함수 및 어셈블리를 형식 라이브러리로 변환 하는 동안 내보내기 도구를 사용 하는 인터페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6bd-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f6bd-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0f6bd-105">In This Section</span></span>  
 [<span data-ttu-id="0f6bd-106">GetTypeLibInfo 함수</span><span class="sxs-lookup"><span data-stu-id="0f6bd-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="0f6bd-107">형식 라이브러리에 대 한 지역화 및 운영 체제 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6bd-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="0f6bd-108">LoadTypeLibWithResolver 함수</span><span class="sxs-lookup"><span data-stu-id="0f6bd-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="0f6bd-109">구현을 사용 하 여 형식 라이브러리를 로드는 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 해결 하려면 형식 라이브러리를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6bd-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="0f6bd-110">ITypeLibResolver 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f6bd-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="0f6bd-111">제공 된 [ResolveTypeLib 메서드](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), 형식 라이브러리의 정규화 된 경로 반환 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f6bd-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
