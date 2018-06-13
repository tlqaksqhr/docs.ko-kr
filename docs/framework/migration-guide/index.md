---
title: '.NET Framework 4.7, 4.6 및 4.5 마이그레이션 가이드 '
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ef6d73aa6cd044cf6808878bf6142a735d015c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391251"
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a><span data-ttu-id="29e96-102">.NET Framework 4.7, 4.6 및 4.5 마이그레이션 가이드</span><span class="sxs-lookup"><span data-stu-id="29e96-102">Migration Guide to the .NET Framework 4.7, 4.6, and 4.5</span></span> 
<span data-ttu-id="29e96-103">이전 버전의 .NET Framework를 사용하여 앱을 만든 경우, 일반적으로 .NET Framework 4.5 및 해당 포인트 릴리스(4.5.1 및 4.5.2), .NET Framework 4.6 및 해당 포인트 릴리스(4.6.1 및 4.6.2) 또는 .NET Framework 4.7 및 해당 포인트 릴리스(4.7.1 및 4.7.2)로 쉽게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-103">If you created your app using an earlier version of the .NET Framework, you can generally upgrade it to the .NET Framework 4.5 and its point releases (4.5.1 and 4.5.2), the .NET Framework 4.6 and its point releases (4.6.1 and 4.6.2), or the .NET Framework 4.7 and its point releases (4.7.1 and 4.7.2) easily.</span></span> <span data-ttu-id="29e96-104">Visual Studio에서 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-104">Open your project in Visual Studio.</span></span> <span data-ttu-id="29e96-105">프로젝트가 이전 버전의 Visual Studio에서 만들어진 경우 **프로젝트 호환성** 대화 상자가 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-105">If your project was created in an earlier version of Visual Studio, the **Project Compatibility** dialog box automatically opens.</span></span> <span data-ttu-id="29e96-106">Visual Studio에서 프로젝트를 업그레이드하는 방법에 대한 자세한 내용은 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) 및 [Visual Studio 2017 플랫폼 대상 지정 및 호환성](/visualstudio/productinfo/vs2017-compatibility-vs)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="29e96-106">For more information about upgrading a project in Visual Studio, see [Port, Migrate, and Upgrade Visual Studio Projects](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) and [Visual Studio 2017 Platform Targeting and Compatibility](/visualstudio/productinfo/vs2017-compatibility-vs).</span></span>  
  
 <span data-ttu-id="29e96-107">그러나 .NET Framework에서 일부 사항을 변경하려면 코드를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-107">However, some changes in the .NET Framework require changes to your code.</span></span> <span data-ttu-id="29e96-108">.NET Framework 4.5 및 해당 포인트 릴리스, .NET Framework 4.6 및 해당 포인트 릴리스 또는 .NET Framework 4.7 및 해당 포인트 릴리스의 새로운 기능을 활용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-108">You may also want to take advantage of functionality that is new in the .NET Framework 4.5 and its point releases, in the .NET Framework 4.6 and its point releases, or in the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="29e96-109">새 버전의 .NET Framework용 으로 변경하는 이러한 유형의 작업을 일반적으로 *마이그레이션*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-109">Making these types of changes to your app for a new version of the .NET Framework is typically referred to as *migration*.</span></span> <span data-ttu-id="29e96-110">앱을 마이그레이션할 필요가 없는 경우 다시 컴파일하지 않고 .NET Framework 4.5 이상 버전에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-110">If your app doesn't have to be migrated, you can run it in the .NET Framework 4.5 or a later version without recompiling it.</span></span>  
  
## <a name="migration-resources"></a><span data-ttu-id="29e96-111">마이그레이션 리소스</span><span class="sxs-lookup"><span data-stu-id="29e96-111">Migration resources</span></span>  
 <span data-ttu-id="29e96-112">이전 버전의 .NET Framework에서 버전 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1 또는 4.7.2로 앱을 마이그레이션하기 전에 다음 문서를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="29e96-112">Review the following documents before you migrate your app from earlier versions of the .NET Framework to version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, or 4.7.2:</span></span>  
  
-   <span data-ttu-id="29e96-113">각 버전의 .NET Framework 내부에 있는 CLR 버전을 파악하고 앱을 대상으로 지정하기 위한 지침을 검토하려면 [버전 및 종속성](../../../docs/framework/migration-guide/versions-and-dependencies.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="29e96-113">See [Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md) to understand the CLR version underlying each version of the .NET Framework and to review guidelines for targeting your apps successfully.</span></span>  
  
-   <span data-ttu-id="29e96-114">앱에 영향을 줄 수 있는 런타임 및 대상 변경 관련 변경 내용과 이를 처리하는 방법을 알아보려면 [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)을 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="29e96-114">Review [Application Compatibility](../../../docs/framework/migration-guide/application-compatibility.md) to find out about runtime and retargeting changes that might affect your app and how to handle them.</span></span>  
  
-   <span data-ttu-id="29e96-115">코드에서 더 이상 사용되지 않는 형식 또는 멤버와 권장되는 대체 항목을 확인하려면 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)을 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="29e96-115">Review [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) to determine any types or members in your code that have been made obsolete, and the recommended alternatives.</span></span>  
  
-   <span data-ttu-id="29e96-116">앱에 추가할 수 있는 새 기능에 대한 설명은 [새로운 기능](../../../docs/framework/whats-new/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="29e96-116">See [What's New](../../../docs/framework/whats-new/index.md) for descriptions of new features that you may want to add to your app.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e96-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29e96-117">See Also</span></span>  
 [<span data-ttu-id="29e96-118">응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="29e96-118">Application Compatibility</span></span>](../../../docs/framework/migration-guide/application-compatibility.md)  
 [<span data-ttu-id="29e96-119">.NET Framework 1.1에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="29e96-119">Migrating from the .NET Framework 1.1</span></span>](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [<span data-ttu-id="29e96-120">버전 호환성</span><span class="sxs-lookup"><span data-stu-id="29e96-120">Version Compatibility</span></span>](../../../docs/framework/migration-guide/version-compatibility.md)  
 [<span data-ttu-id="29e96-121">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="29e96-121">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)  
 [<span data-ttu-id="29e96-122">방법: .NET Framework 4 또는 4.5를 지원하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="29e96-122">How to: Configure an App to Support .NET Framework 4 or 4.5</span></span>](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)  
 [<span data-ttu-id="29e96-123">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="29e96-123">What's New</span></span>](../../../docs/framework/whats-new/index.md)  
 [<span data-ttu-id="29e96-124">클래스 라이브러리의 사용되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="29e96-124">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)  
 [<span data-ttu-id="29e96-125">.NET Framework 버전 및 어셈블리 정보</span><span class="sxs-lookup"><span data-stu-id="29e96-125">.NET Framework Version and Assembly Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=201701)  
 <span data-ttu-id="29e96-126">[Microsoft .NET Framework 지원 기간 정책](http://go.microsoft.com/fwlink/?LinkId=196607) [.NET Framework 4 마이그레이션 문제](net-framework-4-migration-issues.md)</span><span class="sxs-lookup"><span data-stu-id="29e96-126">[Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) [.NET Framework 4 migration issues](net-framework-4-migration-issues.md)</span></span>
