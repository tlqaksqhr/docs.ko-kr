---
title: 1104 - WorkflowActivityResume
ms.date: 03/30/2017
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
ms.openlocfilehash: 4c9ae5fd386fc93ea19578097aa4e0afdda527e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511058"
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="c0c4c-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="c0c4c-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="c0c4c-103">속성</span><span class="sxs-lookup"><span data-stu-id="c0c4c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0c4c-104">ID</span><span class="sxs-lookup"><span data-stu-id="c0c4c-104">ID</span></span>|<span data-ttu-id="c0c4c-105">1104</span><span class="sxs-lookup"><span data-stu-id="c0c4c-105">1104</span></span>|  
|<span data-ttu-id="c0c4c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c0c4c-106">Keywords</span></span>|<span data-ttu-id="c0c4c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c0c4c-107">WFRuntime</span></span>|  
|<span data-ttu-id="c0c4c-108">수준</span><span class="sxs-lookup"><span data-stu-id="c0c4c-108">Level</span></span>|<span data-ttu-id="c0c4c-109">정보</span><span class="sxs-lookup"><span data-stu-id="c0c4c-109">Information</span></span>|  
|<span data-ttu-id="c0c4c-110">채널</span><span class="sxs-lookup"><span data-stu-id="c0c4c-110">Channel</span></span>|<span data-ttu-id="c0c4c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="c0c4c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c0c4c-112">설명</span><span class="sxs-lookup"><span data-stu-id="c0c4c-112">Description</span></span>  
 <span data-ttu-id="c0c4c-113">워크플로 작업이 다시 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0c4c-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c0c4c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c0c4c-114">Message</span></span>  
 <span data-ttu-id="c0c4c-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="c0c4c-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="c0c4c-116">설명</span><span class="sxs-lookup"><span data-stu-id="c0c4c-116">Details</span></span>  
  
|<span data-ttu-id="c0c4c-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c0c4c-117">Data Item Name</span></span>|<span data-ttu-id="c0c4c-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c0c4c-118">Data Item Type</span></span>|<span data-ttu-id="c0c4c-119">설명</span><span class="sxs-lookup"><span data-stu-id="c0c4c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c0c4c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="c0c4c-120">WorkflowInstanceId</span></span>|<span data-ttu-id="c0c4c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c0c4c-121">xs:string</span></span>|<span data-ttu-id="c0c4c-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c0c4c-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="c0c4c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c0c4c-123">AppDomain</span></span>|<span data-ttu-id="c0c4c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c0c4c-124">xs:string</span></span>|<span data-ttu-id="c0c4c-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c0c4c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
