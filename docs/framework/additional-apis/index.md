---
title: "추가 클래스 라이브러리 및 API"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c22de3ed401e0be10b155649395da43cedb35e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="3964f-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="3964f-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="3964f-103">.NET Framework는 계속 진화하고 있으며 플랫폼 간 개발을 향상시키거나 고객에게 새 기능을 일찍 소개하기 위해 새로운 기능인 OOB(대역 외)를 릴리스했습니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="3964f-104">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="3964f-105">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="3964f-106">예를 들어는 <xref:System.Text.CodePagesEncodingProvider> 클래스를 사용 하면 코드 페이지 인코딩.NET Framework를 사용 하 여 개발 하는 UWP 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="3964f-107">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="3964f-108">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="3964f-108">OOB projects</span></span>
  
| <span data-ttu-id="3964f-109">프로젝트</span><span class="sxs-lookup"><span data-stu-id="3964f-109">Project</span></span> | <span data-ttu-id="3964f-110">설명</span><span class="sxs-lookup"><span data-stu-id="3964f-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="3964f-111">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="3964f-112">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="3964f-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="3964f-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="3964f-114">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="3964f-115">TPL 데이터 흐름 라이브러리는 동시성 사용 응용 프로그램의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="3964f-116">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3964f-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="3964f-117">프로젝트</span><span class="sxs-lookup"><span data-stu-id="3964f-117">Project</span></span> | <span data-ttu-id="3964f-118">설명</span><span class="sxs-lookup"><span data-stu-id="3964f-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="3964f-119">확장 된 <xref:System.Text.EncodingProvider> 클래스 코드 페이지 인코딩 유니버설 Windows 플랫폼을 대상으로 하는 앱에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="3964f-120">전용 API</span><span class="sxs-lookup"><span data-stu-id="3964f-120">Private APIs</span></span>  

<span data-ttu-id="3964f-121">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3964f-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="3964f-122">API 이름</span><span class="sxs-lookup"><span data-stu-id="3964f-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="3964f-123">System.Net.Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="3964f-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="3964f-124">System.Net.Connection.m\_WriteList 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="3964f-125">System.Net.ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="3964f-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="3964f-126">System.Net.ConnectionGroup.m\_ConnectionList 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="3964f-127">System.Net.HttpWebRequest 합니다. \_HttpResponse 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-127">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="3964f-128">System.Net.HttpWebRequest 합니다. \_AutoRedirects 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-128">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="3964f-129">System.Net.ServicePoint.m\_ConnectionGroupList 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-129">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="3964f-130">System.Net.ServicePointManager.s\_ServicePointTable 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-130">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="3964f-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes 필드</span><span class="sxs-lookup"><span data-stu-id="3964f-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="3964f-132">System.Windows.Forms.Design.DataMemberFieldEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="3964f-132">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="3964f-133">System.Windows.Forms.Design.DataMemberListEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="3964f-133">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="3964f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3964f-134">See also</span></span>

[<span data-ttu-id="3964f-135">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="3964f-135">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
