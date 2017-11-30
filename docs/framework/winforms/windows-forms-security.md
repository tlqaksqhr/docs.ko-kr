---
title: "Windows Forms 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cdac074b873d3a627e6971d440fdd1f98952b08
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="windows-forms-security"></a><span data-ttu-id="14aff-102">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="14aff-102">Windows Forms Security</span></span>
<span data-ttu-id="14aff-103">Windows Forms 보안 모델 코드 기반 (보안 수준이 설정 되는 코드를 실행 하는 사용자에 관계 없이 코드에 대 한)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="14aff-104">에 컴퓨터 시스템에 이미 있을 수 있는 모든 보안 스키마 외에도입니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="14aff-105">브라우저 (예: 영역을 기반으로 보안 Internet Explorer에서 사용할 수 있는) 또는 운영 체제 (예: Windows NT의 자격 증명 기반 보안용)를 포함할 수 있습니다 이러한.</span><span class="sxs-lookup"><span data-stu-id="14aff-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14aff-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="14aff-106">In This Section</span></span>  
 [<span data-ttu-id="14aff-107">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="14aff-107">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 <span data-ttu-id="14aff-108">Windows Forms 응용 프로그램에서 확인 하는 데 필요한 기본 단계 및.NET Framework 보안 모델은 안전 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="14aff-109">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="14aff-109">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="14aff-110">파일 및 부분 신뢰 환경에서 데이터에에서 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="14aff-111">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="14aff-111">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="14aff-112">부분 신뢰 환경에서 인쇄 기능을 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="14aff-113">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="14aff-113">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="14aff-114">창 조작 수행, 클립보드 사용 및 부분 신뢰 환경에서 비관리 코드로 호출을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14aff-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="14aff-115">Related Sections</span></span>  
 [<span data-ttu-id="14aff-116">NIB: 기본 보안 정책</span><span class="sxs-lookup"><span data-stu-id="14aff-116">NIB: Default Security Policy</span></span>](http://msdn.microsoft.com/en-us/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 <span data-ttu-id="14aff-117">완전 신뢰, 로컬 인트라넷 및 인터넷 권한 집합에 부여 된 기본 사용 권한을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 [<span data-ttu-id="14aff-118">NIB: 일반 보안 정책 관리</span><span class="sxs-lookup"><span data-stu-id="14aff-118">NIB: General Security Policy Administration</span></span>](http://msdn.microsoft.com/en-us/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 <span data-ttu-id="14aff-119">.NET Framework 보안 정책 관리 및 권한 상승에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="14aff-120">위험한 권한 및 정책 관리</span><span class="sxs-lookup"><span data-stu-id="14aff-120">Dangerous Permissions and Policy Administration</span></span>](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="14aff-121">일부 보안 시스템을 손상 시킬 수 있는.net Framework 사용 권한에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="14aff-122">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="14aff-122">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="14aff-123">.NET Framework에 대 한 코드를 안전 하 게 작성 하기 위한 모범 사례를 설명 하는 항목 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 [<span data-ttu-id="14aff-124">NIB: 권한 요청</span><span class="sxs-lookup"><span data-stu-id="14aff-124">NIB: Requesting Permissions</span></span>](http://msdn.microsoft.com/en-us/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 <span data-ttu-id="14aff-125">코드를 실행 해야 합니다. 사용 권한을 런타임에 알려 주는 특성을 사용 하 여를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="14aff-126">주요 보안 개념</span><span class="sxs-lookup"><span data-stu-id="14aff-126">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="14aff-127">코드 보안의 기본 사항을 설명 하는 항목 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="14aff-128">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="14aff-128">Code Access Security Basics</span></span>](../../../docs/framework/misc/code-access-security-basics.md)  
 <span data-ttu-id="14aff-129">실행 시간 보안 정책이.NET Framework와 함께 작업의 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 [<span data-ttu-id="14aff-130">NIB: 보안 정책을 수정 시기 결정</span><span class="sxs-lookup"><span data-stu-id="14aff-130">NIB: Determining When to Modify Security Policy</span></span>](http://msdn.microsoft.com/en-us/af749b17-e461-409d-84b9-a3d44789db16)  
 <span data-ttu-id="14aff-131">응용 프로그램의 기본 보안 정책에서 분기 해야 할 시기를 결정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 [<span data-ttu-id="14aff-132">NIB: 보안 정책 배포</span><span class="sxs-lookup"><span data-stu-id="14aff-132">NIB: Deploying Security Policy</span></span>](http://msdn.microsoft.com/en-us/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 <span data-ttu-id="14aff-133">보안 정책 변경 내용을 배포 하기 위한 최상의 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14aff-133">Discusses the best manner for deploying security policy changes.</span></span>
