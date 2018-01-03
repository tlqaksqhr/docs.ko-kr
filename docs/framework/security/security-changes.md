---
title: ".NET Framework의 보안 변경 내용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
caps.latest.revision: "52"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0777b2566337427abd116bb3584bc19e67d34803
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="4fcdd-102">.NET Framework의 보안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="4fcdd-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="4fcdd-103">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 에서 보안에 대한 가장 중요한 변경 내용은 강력한 이름 지정입니다.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-103">The most important change to security in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is in strong naming.</span></span> <span data-ttu-id="4fcdd-104">변경에 대한 설명은 [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-104">See [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="4fcdd-105">.NET Framework는 관리되는 응용 프로그램에 대한 2계층 보안 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]<span data-ttu-id="4fcdd-106"> 응용 프로그램은 리소스에 대한 액세스를 제한하는 Windows 보안 컨테이너에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-106"> apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="4fcdd-107">해당 컨테이너 내에서 관리되는 응용 프로그램은 완전히 신뢰할 수 있는 상태로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="4fcdd-108">CAS(코드 액세스 보안) 측면에서 개발자가 권한을 높이기 위해 수행할 수 있는 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="4fcdd-109">Windows에서 부여된 권한에 대한 자세한 내용은 Windows 개발자 센터의 [앱 기능 선언(Windows 스토어 앱)](http://go.microsoft.com/fwlink/?LinkId=230436) 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](http://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="4fcdd-110">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱 만들기에 대한 자세한 내용은 [C# 또는 Visual Basic을 사용하여 첫 Windows 스토어 앱 만들기](http://go.microsoft.com/fwlink/?LinkId=230461)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fcdd-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
