---
title: ".NET Framework의 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, security
- security [.NET Framework], about security
- application development [.NET Framework], security
- security [.NET Framework]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
caps.latest.revision: "37"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7f8600da624ff75ce2dbd5c417f886d6b3b1ac37
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="security-in-the-net-framework"></a><span data-ttu-id="d62bb-102">.NET Framework의 보안</span><span class="sxs-lookup"><span data-stu-id="d62bb-102">Security in the .NET Framework</span></span>
<span data-ttu-id="d62bb-103">공용 언어 런타임 및.NET Framework는 개발자가 쉽게 안전한 코드를 작성할 수 있게 해주고 시스템 관리자가 보호된 리소스에 액세스할 수 있도록 코드에 부여되는 권한을 사용자 지정할 수 있게 해주는 많은 유용한 클래스 및 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-103">The common language runtime and the .NET Framework provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="d62bb-104">또한 런타임 및 .NET Framework는 암호화 및 역할 기반 보안을 쉽게 사용할 수 있게 해주는 유용한 클래스 및 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-104">In addition, the runtime and the .NET Framework provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d62bb-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d62bb-105">In This Section</span></span>  
 [<span data-ttu-id="d62bb-106">보안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d62bb-106">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)  
 <span data-ttu-id="d62bb-107">.NET Framework 보안 시스템과 관련된 중요 변경 내용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-107">Describes important changes to the .NET Framework security system.</span></span>  
  
 [<span data-ttu-id="d62bb-108">주요 보안 개념</span><span class="sxs-lookup"><span data-stu-id="d62bb-108">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="d62bb-109">공용 언어 런타임 보안 기능에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="d62bb-110">이 섹션은 개발자와 시스템 관리자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-110">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="d62bb-111">역할 기반 보안</span><span class="sxs-lookup"><span data-stu-id="d62bb-111">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="d62bb-112">코드에서 역할 기반 보안과 상호 작용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="d62bb-113">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-113">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="d62bb-114">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="d62bb-114">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="d62bb-115">.NET Framework에서 제공하는 암호화 서비스에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-115">Provides an overview of cryptographic services provided by the .NET Framework.</span></span> <span data-ttu-id="d62bb-116">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-116">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="d62bb-117">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="d62bb-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="d62bb-118">신뢰할 수 있는 .NET Framework 응용 프로그램을 만들기 위한 몇 가지 모범 사례를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-118">Describes some of the best practices for creating reliable .NET Framework applications.</span></span> <span data-ttu-id="d62bb-119">이 섹션은 개발자에게 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-119">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="d62bb-120">비관리 코드에 대한 보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="d62bb-120">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="d62bb-121">비관리 코드를 호출할 때 모범 사례 및 보안 고려 사항 중 일부에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-121">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="d62bb-122">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d62bb-122">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="d62bb-123">응용 프로그램에서 클레임 기반 ID를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-123">Describes how you can implement claims-based identity in your applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d62bb-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d62bb-124">Related Sections</span></span>  
 [<span data-ttu-id="d62bb-125">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="d62bb-125">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="d62bb-126">만들기, 구성, 디버깅, 보안, 응용 프로그램 배포, 동적 프로그래밍에 대한 정보, 상호 운용성, 확장성, 메모리 관리 및 스레딩을 포함하여 응용 프로그램 개발에 대한 모든 주요 기술 분야 및 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d62bb-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
