---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: d294ba4f14472012b9e311ee53742633b5173f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485820"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="2f67a-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="2f67a-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="2f67a-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="2f67a-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f67a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f67a-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2f67a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2f67a-105">Methods</span></span>  
 <span data-ttu-id="2f67a-106">DeliveryRequirementsAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2f67a-107">속성</span><span class="sxs-lookup"><span data-stu-id="2f67a-107">Properties</span></span>  
 <span data-ttu-id="2f67a-108">DeliveryRequirementsAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="2f67a-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="2f67a-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="2f67a-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2f67a-110">Data type: string</span></span>  
  
 <span data-ttu-id="2f67a-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2f67a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f67a-112">서비스 바인딩이 계약을 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="2f67a-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="2f67a-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="2f67a-114">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="2f67a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="2f67a-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2f67a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f67a-116">바인딩이 순서가 지정된 메시지를 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="2f67a-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="2f67a-117">TargetContract</span></span>  
 <span data-ttu-id="2f67a-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2f67a-118">Data type: string</span></span>  
  
 <span data-ttu-id="2f67a-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2f67a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f67a-120">적용할 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f67a-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f67a-121">Requirements</span></span>  
  
|<span data-ttu-id="2f67a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2f67a-122">MOF</span></span>|<span data-ttu-id="2f67a-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2f67a-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2f67a-124">Namespace</span></span>|<span data-ttu-id="2f67a-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f67a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f67a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f67a-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
