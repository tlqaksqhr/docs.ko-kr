---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 24184c24b9affdf3a56d7968c02cf5354d690749
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458837"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="42df5-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="42df5-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="42df5-103">속성</span><span class="sxs-lookup"><span data-stu-id="42df5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42df5-104">ID</span><span class="sxs-lookup"><span data-stu-id="42df5-104">ID</span></span>|<span data-ttu-id="42df5-105">209</span><span class="sxs-lookup"><span data-stu-id="42df5-105">209</span></span>|  
|<span data-ttu-id="42df5-106">키워드</span><span class="sxs-lookup"><span data-stu-id="42df5-106">Keywords</span></span>|<span data-ttu-id="42df5-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="42df5-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="42df5-108">수준</span><span class="sxs-lookup"><span data-stu-id="42df5-108">Level</span></span>|<span data-ttu-id="42df5-109">정보</span><span class="sxs-lookup"><span data-stu-id="42df5-109">Information</span></span>|  
|<span data-ttu-id="42df5-110">채널</span><span class="sxs-lookup"><span data-stu-id="42df5-110">Channel</span></span>|<span data-ttu-id="42df5-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="42df5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42df5-112">설명</span><span class="sxs-lookup"><span data-stu-id="42df5-112">Description</span></span>  
 <span data-ttu-id="42df5-113">이 이벤트는 서비스 모델이 메시지 검사자에 대해 `BeforeSend` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="42df5-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42df5-114">메시지</span><span class="sxs-lookup"><span data-stu-id="42df5-114">Message</span></span>  
 <span data-ttu-id="42df5-115">디스패처가 '%1' 형식의 MessageInspector에 대해 'BeforeSendRequest'를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="42df5-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42df5-116">설명</span><span class="sxs-lookup"><span data-stu-id="42df5-116">Details</span></span>  
  
|<span data-ttu-id="42df5-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="42df5-117">Data Item Name</span></span>|<span data-ttu-id="42df5-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="42df5-118">Data Item Type</span></span>|<span data-ttu-id="42df5-119">설명</span><span class="sxs-lookup"><span data-stu-id="42df5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42df5-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="42df5-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="42df5-121">호출된 `MessageInspector` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="42df5-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="42df5-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="42df5-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="42df5-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="42df5-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="42df5-124">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="42df5-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="42df5-125">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="42df5-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="42df5-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42df5-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="42df5-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42df5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
