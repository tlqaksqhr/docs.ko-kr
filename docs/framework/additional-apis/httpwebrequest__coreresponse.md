---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="d8f95-102">HttpWebRequest 합니다. \_CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="d8f95-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="d8f95-103">`HttpWebRequest._CoreResponse`개체 (중 하나는 [CoreResponseData](coreresponsedata.md) 또는 <xref:System.Exception>) HTTP 응답을 구문 분석의 결과가 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f95-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8f95-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8f95-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="d8f95-105">이 API는 사용자 코드에서 직접 사용할 수는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f95-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="d8f95-106">를 대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f95-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="d8f95-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f95-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="d8f95-108">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f95-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d8f95-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8f95-109">Requirements</span></span>

<span data-ttu-id="d8f95-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d8f95-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d8f95-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="d8f95-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d8f95-112">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f95-112">**.NET Framework versions:** Available since 2.0.</span></span>
