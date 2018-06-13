---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509797"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="c4fc8-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="c4fc8-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="c4fc8-103">속성</span><span class="sxs-lookup"><span data-stu-id="c4fc8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4fc8-104">ID</span><span class="sxs-lookup"><span data-stu-id="c4fc8-104">ID</span></span>|<span data-ttu-id="c4fc8-105">1001</span><span class="sxs-lookup"><span data-stu-id="c4fc8-105">1001</span></span>|  
|<span data-ttu-id="c4fc8-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c4fc8-106">Keywords</span></span>|<span data-ttu-id="c4fc8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c4fc8-107">WFRuntime</span></span>|  
|<span data-ttu-id="c4fc8-108">수준</span><span class="sxs-lookup"><span data-stu-id="c4fc8-108">Level</span></span>|<span data-ttu-id="c4fc8-109">정보</span><span class="sxs-lookup"><span data-stu-id="c4fc8-109">Information</span></span>|  
|<span data-ttu-id="c4fc8-110">채널</span><span class="sxs-lookup"><span data-stu-id="c4fc8-110">Channel</span></span>|<span data-ttu-id="c4fc8-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="c4fc8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c4fc8-112">설명</span><span class="sxs-lookup"><span data-stu-id="c4fc8-112">Description</span></span>  
 <span data-ttu-id="c4fc8-113">워크플로 응용 프로그램이 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4fc8-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c4fc8-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c4fc8-114">Message</span></span>  
 <span data-ttu-id="c4fc8-115">WorkflowInstance Id: '%1'이(가) Closed 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c4fc8-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c4fc8-116">설명</span><span class="sxs-lookup"><span data-stu-id="c4fc8-116">Details</span></span>  
  
|<span data-ttu-id="c4fc8-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c4fc8-117">Data Item Name</span></span>|<span data-ttu-id="c4fc8-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c4fc8-118">Data Item Type</span></span>|<span data-ttu-id="c4fc8-119">설명</span><span class="sxs-lookup"><span data-stu-id="c4fc8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c4fc8-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="c4fc8-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="c4fc8-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="c4fc8-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="c4fc8-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c4fc8-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c4fc8-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c4fc8-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
