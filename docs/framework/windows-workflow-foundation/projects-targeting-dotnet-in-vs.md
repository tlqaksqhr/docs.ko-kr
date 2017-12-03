---
title: "Visual Studio 2010에서 .NET Framework 버전 3.0 및 3.5를 대상으로 하는 프로젝트 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc6657bad5cc11eaa723c733319673468749b79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a><span data-ttu-id="b0acd-102">Visual Studio 2010에서 .NET Framework 버전 3.0 및 3.5를 대상으로 하는 프로젝트 작성</span><span class="sxs-lookup"><span data-stu-id="b0acd-102">Writing Projects Targeting the .NET Framework 3.0 and 3.5 in Visual Studio 2010</span></span>
<span data-ttu-id="b0acd-103">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]을 사용하여 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 버전 3.0 또는 3.5를 대상으로 하는 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-103">You can use [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] to create projects that target the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] version 3.0 or 3.5.</span></span> <span data-ttu-id="b0acd-104">이 항목에서는 이 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-104">This topic describes how to do this.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0acd-105">활동을 추가할 때 원하는 버전의 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]가 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b0acd-105">When adding activities, make sure that the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] is set.</span></span> <span data-ttu-id="b0acd-106">활동이 추가된 후 워크플로의 대상 버전을 변경하면 워크플로의 유효성 검사가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-106">Changing the target version of the workflow after activities are added will cause the workflow to fail validation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b0acd-107">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]에서 .NET Framework 3.5 활동이 있는 기존 워크플로를 열면 `this.SetValue()`에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-107">Opening existing workflows in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] that have .Net Framework 3.5 activities will cause an error at `this.SetValue()`.</span></span> <span data-ttu-id="b0acd-108">이전 버전의 .NET Framework에서 만든 프로젝트를 열려면 먼저 디자이너에서 빈 워크플로를 열고 .NET Framework 3.5 활동을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-108">In order to open projects created with previous versions of the .Net Framework, first open a blank workflow in the designer and add a .Net Framework 3.5 activity.</span></span>  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a><span data-ttu-id="b0acd-109">Visual Studio 2010에서 .NET Framework 3.0 또는 3.5 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b0acd-109">To create a .NET Framework  3.0 or 3.5 project with Visual Studio 2010</span></span>  
  
1.  <span data-ttu-id="b0acd-110">[!INCLUDE[vs2010](../../../includes/vs2010-md.md)]를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-110">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b0acd-111">선택 **파일**, **새**, **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-111">Select **File**, **New**, **Project**.</span></span>  
  
3.  <span data-ttu-id="b0acd-112">대화 상자 위쪽의 드롭다운 목록에서 적절한 버전의 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-112">In the drop-down list at the top of the dialog box, select the desired version of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a><span data-ttu-id="b0acd-113">.NET Framework의 대상 버전을 업그레이드하려면</span><span class="sxs-lookup"><span data-stu-id="b0acd-113">To upgrade the targeted version of the .NET Framework</span></span>  
  
1.  <span data-ttu-id="b0acd-114">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-114">Right-click the project in Solution Explorer, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b0acd-115">에 **대상 프레임 워크** 드롭 다운 목록에서 원하는 버전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0acd-115">In the **Target Framework** drop-down list, select the desired version.</span></span>
