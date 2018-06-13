---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d1eaf3cf107a6b5e244cc2d9372ee68d387ef6c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510668"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="e18ad-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="e18ad-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="e18ad-103">속성</span><span class="sxs-lookup"><span data-stu-id="e18ad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e18ad-104">ID</span><span class="sxs-lookup"><span data-stu-id="e18ad-104">ID</span></span>|<span data-ttu-id="e18ad-105">1004</span><span class="sxs-lookup"><span data-stu-id="e18ad-105">1004</span></span>|  
|<span data-ttu-id="e18ad-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e18ad-106">Keywords</span></span>|<span data-ttu-id="e18ad-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e18ad-107">WFRuntime</span></span>|  
|<span data-ttu-id="e18ad-108">수준</span><span class="sxs-lookup"><span data-stu-id="e18ad-108">Level</span></span>|<span data-ttu-id="e18ad-109">정보</span><span class="sxs-lookup"><span data-stu-id="e18ad-109">Information</span></span>|  
|<span data-ttu-id="e18ad-110">채널</span><span class="sxs-lookup"><span data-stu-id="e18ad-110">Channel</span></span>|<span data-ttu-id="e18ad-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="e18ad-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e18ad-112">설명</span><span class="sxs-lookup"><span data-stu-id="e18ad-112">Description</span></span>  
 <span data-ttu-id="e18ad-113">워크플로 인스턴스가 예외와 함께 중단되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e18ad-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e18ad-114">메시지</span><span class="sxs-lookup"><span data-stu-id="e18ad-114">Message</span></span>  
 <span data-ttu-id="e18ad-115">WorkflowInstance Id: '%1'이(가) 예외와 함께 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e18ad-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e18ad-116">설명</span><span class="sxs-lookup"><span data-stu-id="e18ad-116">Details</span></span>  
  
|<span data-ttu-id="e18ad-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e18ad-117">Data Item Name</span></span>|<span data-ttu-id="e18ad-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e18ad-118">Data Item Type</span></span>|<span data-ttu-id="e18ad-119">설명</span><span class="sxs-lookup"><span data-stu-id="e18ad-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e18ad-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e18ad-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="e18ad-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="e18ad-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="e18ad-122">예외</span><span class="sxs-lookup"><span data-stu-id="e18ad-122">Exception</span></span>|`xs:string`|<span data-ttu-id="e18ad-123">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="e18ad-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="e18ad-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e18ad-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e18ad-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e18ad-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
