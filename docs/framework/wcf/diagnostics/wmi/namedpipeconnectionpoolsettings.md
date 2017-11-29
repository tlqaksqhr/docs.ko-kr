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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf9c39334289cb30d1a01917c0be37da02fcdc5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="48799-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="48799-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="48799-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="48799-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48799-104">구문</span><span class="sxs-lookup"><span data-stu-id="48799-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="48799-105">메서드</span><span class="sxs-lookup"><span data-stu-id="48799-105">Methods</span></span>  
 <span data-ttu-id="48799-106">NamedPipeConnectionPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48799-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="48799-107">속성</span><span class="sxs-lookup"><span data-stu-id="48799-107">Properties</span></span>  
 <span data-ttu-id="48799-108">NamedPipeConnectionPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48799-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="48799-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="48799-109">GroupName</span></span>  
 <span data-ttu-id="48799-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="48799-110">Data type: string</span></span>  
  
 <span data-ttu-id="48799-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="48799-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48799-112">바인딩 요소가 사용하는 연결 풀의 그룹 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48799-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="48799-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="48799-113">IdleTimeout</span></span>  
 <span data-ttu-id="48799-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="48799-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="48799-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="48799-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48799-116">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="48799-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="48799-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="48799-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="48799-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="48799-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="48799-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="48799-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48799-120">클라이언트에서 각 끝점에 대한 최대 아웃바운드 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48799-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48799-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48799-121">Requirements</span></span>  
  
|<span data-ttu-id="48799-122">MOF</span><span class="sxs-lookup"><span data-stu-id="48799-122">MOF</span></span>|<span data-ttu-id="48799-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48799-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="48799-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="48799-124">Namespace</span></span>|<span data-ttu-id="48799-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48799-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48799-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48799-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
