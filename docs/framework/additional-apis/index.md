---
title: 추가 클래스 라이브러리 및 API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdba02feb8cacc6ab1886c12f88716184aa2a81a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="26b95-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="26b95-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="26b95-103">.NET Framework는 계속 진화하고 있으며 플랫폼 간 개발을 향상시키거나 고객에게 새 기능을 일찍 소개하기 위해 새로운 기능인 OOB(대역 외)를 릴리스했습니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="26b95-104">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="26b95-105">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="26b95-106">예를 들어는 <xref:System.Text.CodePagesEncodingProvider> 클래스를 사용 하면 코드 페이지 인코딩.NET Framework를 사용 하 여 개발 하는 UWP 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="26b95-107">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="26b95-108">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="26b95-108">OOB projects</span></span>
  
| <span data-ttu-id="26b95-109">프로젝트</span><span class="sxs-lookup"><span data-stu-id="26b95-109">Project</span></span> | <span data-ttu-id="26b95-110">설명</span><span class="sxs-lookup"><span data-stu-id="26b95-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="26b95-111">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="26b95-112">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="26b95-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="26b95-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="26b95-114">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="26b95-115">TPL 데이터 흐름 라이브러리는 동시성 사용 응용 프로그램의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="26b95-116">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="26b95-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="26b95-117">프로젝트</span><span class="sxs-lookup"><span data-stu-id="26b95-117">Project</span></span> | <span data-ttu-id="26b95-118">설명</span><span class="sxs-lookup"><span data-stu-id="26b95-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="26b95-119">확장 된 <xref:System.Text.EncodingProvider> 클래스 코드 페이지 인코딩 유니버설 Windows 플랫폼을 대상으로 하는 앱에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="26b95-120">전용 API</span><span class="sxs-lookup"><span data-stu-id="26b95-120">Private APIs</span></span>  

<span data-ttu-id="26b95-121">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26b95-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="26b95-122">API 이름</span><span class="sxs-lookup"><span data-stu-id="26b95-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="26b95-123">System.Net.Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="26b95-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="26b95-124">System.Net.Connection.m\_WriteList Field</span><span class="sxs-lookup"><span data-stu-id="26b95-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="26b95-125">System.Net.ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="26b95-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="26b95-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="26b95-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="26b95-127">System.Net.CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="26b95-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="26b95-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="26b95-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="26b95-129">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="26b95-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="26b95-130">System.Net.HttpWebRequest 합니다. \_AutoRedirects 필드</span><span class="sxs-lookup"><span data-stu-id="26b95-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="26b95-131">System.Net.HttpWebRequest 합니다. \_CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="26b95-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="26b95-132">System.Net.HttpWebRequest 합니다. \_HttpResponse 필드</span><span class="sxs-lookup"><span data-stu-id="26b95-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="26b95-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="26b95-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="26b95-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="26b95-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="26b95-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="26b95-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="26b95-136">System.Windows.Forms.Design.DataMemberFieldEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="26b95-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="26b95-137">System.Windows.Forms.Design.DataMemberListEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="26b95-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="26b95-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="26b95-138">See also</span></span>

[<span data-ttu-id="26b95-139">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="26b95-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
