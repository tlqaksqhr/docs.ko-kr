---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 572a19723583a6bc717a71b3b46040148f29e1cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="456c6-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="456c6-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="456c6-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="456c6-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="456c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="456c6-104">Syntax</span></span>  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="456c6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="456c6-105">Methods</span></span>  
 <span data-ttu-id="456c6-106">MsmqTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="456c6-107">속성</span><span class="sxs-lookup"><span data-stu-id="456c6-107">Properties</span></span>  
 <span data-ttu-id="456c6-108">MsmqTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="456c6-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="456c6-109">MaxPoolSize</span></span>  
 <span data-ttu-id="456c6-110">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="456c6-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="456c6-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="456c6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="456c6-112">내부 MSMQ 메시지 개체가 포함된 풀의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="456c6-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="456c6-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="456c6-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="456c6-114">Data type: string</span></span>  
  
 <span data-ttu-id="456c6-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="456c6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="456c6-116">이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="456c6-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="456c6-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="456c6-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="456c6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="456c6-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="456c6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="456c6-120">Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 나타내는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="456c6-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="456c6-121">Requirements</span></span>  
  
|<span data-ttu-id="456c6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="456c6-122">MOF</span></span>|<span data-ttu-id="456c6-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="456c6-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="456c6-124">Namespace</span></span>|<span data-ttu-id="456c6-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="456c6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="456c6-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="456c6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
