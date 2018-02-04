---
title: CoreResponseData.m_StatusCode Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_StatusCode
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 1630fe66152925120f5459276899b1d3e581f05e
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="coreresponsedatamstatuscode-field"></a><span data-ttu-id="a1c1c-102">CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="a1c1c-102">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="a1c1c-103">`CoreResponseData.m_StatusCode`이 <xref:System.Net.HttpStatusCode> 응답의 상태를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c1c-103">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1c1c-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1c1c-104">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="a1c1c-105">이 API는 사용자 코드에서 직접 사용할 수는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c1c-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="a1c1c-106">를 대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c1c-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="a1c1c-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c1c-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="a1c1c-108">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c1c-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1c1c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1c1c-109">Requirements</span></span>

<span data-ttu-id="a1c1c-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a1c1c-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a1c1c-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="a1c1c-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a1c1c-112">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c1c-112">**.NET Framework versions:** Available since 2.0.</span></span>
