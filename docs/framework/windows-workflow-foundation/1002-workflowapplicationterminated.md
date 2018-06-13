---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510081"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="2a958-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="2a958-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="2a958-103">속성</span><span class="sxs-lookup"><span data-stu-id="2a958-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a958-104">ID</span><span class="sxs-lookup"><span data-stu-id="2a958-104">ID</span></span>|<span data-ttu-id="2a958-105">1002</span><span class="sxs-lookup"><span data-stu-id="2a958-105">1002</span></span>|  
|<span data-ttu-id="2a958-106">키워드</span><span class="sxs-lookup"><span data-stu-id="2a958-106">Keywords</span></span>|<span data-ttu-id="2a958-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a958-107">WFRuntime</span></span>|  
|<span data-ttu-id="2a958-108">수준</span><span class="sxs-lookup"><span data-stu-id="2a958-108">Level</span></span>|<span data-ttu-id="2a958-109">정보</span><span class="sxs-lookup"><span data-stu-id="2a958-109">Information</span></span>|  
|<span data-ttu-id="2a958-110">채널</span><span class="sxs-lookup"><span data-stu-id="2a958-110">Channel</span></span>|<span data-ttu-id="2a958-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="2a958-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a958-112">설명</span><span class="sxs-lookup"><span data-stu-id="2a958-112">Description</span></span>  
 <span data-ttu-id="2a958-113">워크플로 응용 프로그램에 예외가 발생하여 오류 상태로 종료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a958-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a958-114">메시지</span><span class="sxs-lookup"><span data-stu-id="2a958-114">Message</span></span>  
 <span data-ttu-id="2a958-115">WorkflowApplication Id: '%1'이(가) 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a958-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="2a958-116">예외가 발생하여 오류 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a958-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a958-117">설명</span><span class="sxs-lookup"><span data-stu-id="2a958-117">Details</span></span>  
  
|<span data-ttu-id="2a958-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2a958-118">Data Item Name</span></span>|<span data-ttu-id="2a958-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2a958-119">Data Item Type</span></span>|<span data-ttu-id="2a958-120">설명</span><span class="sxs-lookup"><span data-stu-id="2a958-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a958-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="2a958-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="2a958-122">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="2a958-122">The workflow application id</span></span>|  
|<span data-ttu-id="2a958-123">예외</span><span class="sxs-lookup"><span data-stu-id="2a958-123">Exception</span></span>|`xs:string`|<span data-ttu-id="2a958-124">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="2a958-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="2a958-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a958-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2a958-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a958-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
