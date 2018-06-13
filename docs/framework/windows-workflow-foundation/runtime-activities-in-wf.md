---
title: WF의 런타임 활동
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513037"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="3e459-102">WF의 런타임 활동</span><span class="sxs-lookup"><span data-stu-id="3e459-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="3e459-103">는 지속성 및 종료와 같이 워크플로 런타임의 기능에 액세스하기 위한 여러 시스템 제공 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e459-103"> provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="3e459-104">동작</span><span class="sxs-lookup"><span data-stu-id="3e459-104">Activity</span></span>|<span data-ttu-id="3e459-105">설명</span><span class="sxs-lookup"><span data-stu-id="3e459-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="3e459-106">워크플로가 상태를 유지하도록 명시적으로 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="3e459-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="3e459-107">실행 중인 워크플로 인스턴스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3e459-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="3e459-108">자식 활동이 유지되지 않도록 하는 컨테이너 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="3e459-108">A container activity that prevents child activities from persisting.</span></span>|
