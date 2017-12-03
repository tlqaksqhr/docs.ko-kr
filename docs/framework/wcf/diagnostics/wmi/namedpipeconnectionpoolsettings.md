---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18740c4c87aaeafcd0a28991376e0c45fe688223
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="adec1-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="adec1-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="adec1-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="adec1-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adec1-104">구문</span><span class="sxs-lookup"><span data-stu-id="adec1-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="adec1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="adec1-105">Methods</span></span>  
 <span data-ttu-id="adec1-106">NamedPipeConnectionPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="adec1-107">속성</span><span class="sxs-lookup"><span data-stu-id="adec1-107">Properties</span></span>  
 <span data-ttu-id="adec1-108">NamedPipeConnectionPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="adec1-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="adec1-109">GroupName</span></span>  
 <span data-ttu-id="adec1-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="adec1-110">Data type: string</span></span>  
  
 <span data-ttu-id="adec1-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adec1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adec1-112">바인딩 요소가 사용하는 연결 풀의 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="adec1-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="adec1-113">IdleTimeout</span></span>  
 <span data-ttu-id="adec1-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="adec1-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="adec1-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adec1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adec1-116">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="adec1-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="adec1-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="adec1-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="adec1-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="adec1-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adec1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adec1-120">클라이언트에서 각 끝점에 대한 최대 아웃바운드 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adec1-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adec1-121">Requirements</span></span>  
  
|<span data-ttu-id="adec1-122">MOF</span><span class="sxs-lookup"><span data-stu-id="adec1-122">MOF</span></span>|<span data-ttu-id="adec1-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="adec1-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="adec1-124">Namespace</span></span>|<span data-ttu-id="adec1-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adec1-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adec1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adec1-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
