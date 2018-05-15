---
title: CoreResponseData.m_ResponseHeaders 필드
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="d847b-102">CoreResponseData.m\_ResponseHeaders 필드</span><span class="sxs-lookup"><span data-stu-id="d847b-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="d847b-103">`CoreResponseData.m_ResponseHeaders` 이 <xref:System.Net.WebHeaderCollection> 연결 된 서버 응답 헤더의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d847b-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="d847b-104">구문</span><span class="sxs-lookup"><span data-stu-id="d847b-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="d847b-105">이 API는 사용자 코드에서 직접 사용할 수는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d847b-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="d847b-106">를 대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d847b-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="d847b-107">참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d847b-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="d847b-108">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d847b-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d847b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d847b-109">Requirements</span></span>

<span data-ttu-id="d847b-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="d847b-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="d847b-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="d847b-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="d847b-112">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d847b-112">**.NET Framework versions:** Available since 2.0.</span></span>
