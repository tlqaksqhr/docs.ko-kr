---
title: "추가 클래스 라이브러리 및 API | Microsoft 문서"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: b53b8acc2a6c56db6a9d8a9b7c685a2d400a53e1
ms.openlocfilehash: 34815268b707aa70d174a1bbc04c32276db8412d
ms.contentlocale: ko-kr
ms.lasthandoff: 05/02/2017

---

# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="eee61-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="eee61-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="eee61-103">.NET Framework는 계속 진화하고 있으며 플랫폼 간 개발을 향상시키거나 고객에게 새 기능을 일찍 소개하기 위해 새로운 기능인 OOB(대역 외)를 릴리스했습니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="eee61-104">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="eee61-105">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="eee61-106">예를 들어, <xref:System.Text.CodePagesEncodingProvider> 클래스는 .NET Framework를 사용하여 개발된 UWP 앱에 사용할 수 있는 코드 페이지 인코딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="eee61-107">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="eee61-108">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="eee61-108">OOB projects</span></span>
  
| <span data-ttu-id="eee61-109">프로젝트</span><span class="sxs-lookup"><span data-stu-id="eee61-109">Project</span></span> | <span data-ttu-id="eee61-110">설명</span><span class="sxs-lookup"><span data-stu-id="eee61-110">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="eee61-111"><xref:System.Collections.Immutable></span><span class="sxs-lookup"><span data-stu-id="eee61-111"><xref:System.Collections.Immutable></span></span> | <span data-ttu-id="eee61-112">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <span data-ttu-id="eee61-113"><xref:System.Net.Http.WinHttpHandler></span><span class="sxs-lookup"><span data-stu-id="eee61-113"><xref:System.Net.Http.WinHttpHandler></span></span> | <span data-ttu-id="eee61-114">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient>에 대한 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-114">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="eee61-115">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="eee61-115">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="eee61-116">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-116">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <span data-ttu-id="eee61-117"><xref:System.Threading.Tasks.Dataflow></span><span class="sxs-lookup"><span data-stu-id="eee61-117"><xref:System.Threading.Tasks.Dataflow></span></span> | <span data-ttu-id="eee61-118">TPL 데이터 흐름 라이브러리는 동시성 사용 응용 프로그램의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-118">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="eee61-119">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="eee61-119">Platform-specific libraries</span></span>
  
| <span data-ttu-id="eee61-120">프로젝트</span><span class="sxs-lookup"><span data-stu-id="eee61-120">Project</span></span> | <span data-ttu-id="eee61-121">설명</span><span class="sxs-lookup"><span data-stu-id="eee61-121">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="eee61-122"><xref:System.Text.CodePagesEncodingProvider></span><span class="sxs-lookup"><span data-stu-id="eee61-122"><xref:System.Text.CodePagesEncodingProvider></span></span> | <span data-ttu-id="eee61-123"><xref:System.Text.EncodingProvider> 클래스를 확장하여 유니버설 Windows 플랫폼을 대상으로 하는 앱에 사용할 수 있는 코드 페이지 인코딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-123">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="eee61-124">전용 API</span><span class="sxs-lookup"><span data-stu-id="eee61-124">Private APIs</span></span>  

<span data-ttu-id="eee61-125">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eee61-125">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="eee61-126">API 이름</span><span class="sxs-lookup"><span data-stu-id="eee61-126">API Name</span></span> |  
| -------- |  
| [<span data-ttu-id="eee61-127">s_isDebuggerCheckDisabledForTestPurposes 필드</span><span class="sxs-lookup"><span data-stu-id="eee61-127">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |  
| [<span data-ttu-id="eee61-128">DataMemberFieldEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="eee61-128">DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |  
| [<span data-ttu-id="eee61-129">DataMemberListEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="eee61-129">DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |  
  
## <a name="see-also"></a><span data-ttu-id="eee61-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eee61-130">See also</span></span>

[<span data-ttu-id="eee61-131">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="eee61-131">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)

