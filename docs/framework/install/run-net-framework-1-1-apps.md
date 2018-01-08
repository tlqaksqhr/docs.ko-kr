---
title: "Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행"
ms.custom: 
ms.date: 05/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d5b99390e62984b37b0d7267c40b1221f556f60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="479c5-102">Windows 8, Windows 8.1 또는 Windows 10에서 .NET Framework 1.1 앱 실행</span><span class="sxs-lookup"><span data-stu-id="479c5-102">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="479c5-103">.NET Framework 1.1은 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] 또는 Windows 10 운영 체제에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-103">The .NET Framework 1.1 is not supported on the [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or the Windows 10 operating systems.</span></span> <span data-ttu-id="479c5-104">앱을 실행하는 데 특별히 .NET Framework 1.1이 필요하다고 확인될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-104">In some cases, the .NET Framework 1.1 is specifically identified as required for an app to run.</span></span> <span data-ttu-id="479c5-105">이 경우 ISV(Independent Software Vendor)에 문의하여 [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] 이상의 버전에서 실행되도록 앱을 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-105">In those cases, you should contact your independent software vendor (ISV) to have the app upgraded to run on the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] or later version.</span></span> <span data-ttu-id="479c5-106">자세한 내용은 [.NET Framework 1.1에서 마이그레이션](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="479c5-106">For additional information, see [Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="479c5-107">CD 또는 다운로드 센터에서 .NET Framework 1.1 설치</span><span class="sxs-lookup"><span data-stu-id="479c5-107">Install the .NET Framework 1.1 from a CD or Download Center</span></span>

<span data-ttu-id="479c5-108">.NET Framework 1.1을 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] 또는 Windows 10에 수동으로 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-108">It isn't possible to manually install the .NET Framework 1.1 on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or Windows 10.</span></span> <span data-ttu-id="479c5-109">더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-109">It is no longer supported.</span></span> <span data-ttu-id="479c5-110">패키지를 설치하려고 하면 다음과 같은 오류 메시지가 표시됩니다. "이 버전의 .NET Framework가 이전에 설치된 버전과 호환되지 않으므로 설치를 계속할 수 없습니다."</span><span class="sxs-lookup"><span data-stu-id="479c5-110">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="479c5-111">이 문제를 해결하려면 [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-111">To solve this problem, install the [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="479c5-112">이 버전에는 [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] 및 Windows 10에서 지원되는 .NET Framework 2.0(.NET Framework 1.1 후속 릴리스)이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-112">This version includes the .NET Framework 2.0 (the release that follows the .NET Framework 1.1), which is supported on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], and Windows 10.</span></span> <span data-ttu-id="479c5-113">항상 먼저 앱을 설치하여 .NET Framework의 이후 버전으로 자동으로 업데이트되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="479c5-113">You should always try to install the app first to determine if it will automatically be updated to a later version of the .NET Framework.</span></span> <span data-ttu-id="479c5-114">그러지 않으면 ISV에 앱 업데이트에 대해 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="479c5-114">If it does not, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="479c5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="479c5-115">See also</span></span>

<span data-ttu-id="479c5-116">[.NET Framework 1.1에서 마이그레이션](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치](../../../docs/framework/install/dotnet-35-windows-10.md)</span><span class="sxs-lookup"><span data-stu-id="479c5-116">[Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span></span>
