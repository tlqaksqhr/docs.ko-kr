---
title: CoreResponseData 클래스
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 640a925c3aec86b4743b1b2b62eb3793af1cc0bb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742207"
---
# <a name="coreresponsedata-class"></a><span data-ttu-id="5e847-102">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="5e847-102">CoreResponseData Class</span></span>

<span data-ttu-id="5e847-103">`CoreResponseData` HTTP 헤더 및 응답 본문의 구문 분석 하는 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e847-103">The `CoreResponseData` class represents the parsing of the HTTP headers and the response body.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e847-104">구문</span><span class="sxs-lookup"><span data-stu-id="5e847-104">Syntax</span></span>
  
```csharp
internal class CoreResponseData
```

> [!WARNING]
> <span data-ttu-id="5e847-105">이 API는 내부 하며 사용자 코드에서 직접 사용할 수 다루지는지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e847-105">This API is internal, and it is not meant to be used directly in your code.</span></span> <span data-ttu-id="5e847-106">를 대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e847-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="5e847-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e847-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="5e847-108">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e847-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e847-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5e847-109">Requirements</span></span>

<span data-ttu-id="5e847-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="5e847-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="5e847-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="5e847-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="5e847-112">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e847-112">**.NET Framework versions:** Available since 2.0.</span></span>
