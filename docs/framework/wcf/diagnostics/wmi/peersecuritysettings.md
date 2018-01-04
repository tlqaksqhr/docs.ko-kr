---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="c1ad1-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="c1ad1-102">PeerSecuritySettings</span></span>
<span data-ttu-id="c1ad1-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="c1ad1-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ad1-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1ad1-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c1ad1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c1ad1-105">Methods</span></span>  
 <span data-ttu-id="c1ad1-106">PeerSecuritySettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ad1-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c1ad1-107">속성</span><span class="sxs-lookup"><span data-stu-id="c1ad1-107">Properties</span></span>  
 <span data-ttu-id="c1ad1-108">PeerSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ad1-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="c1ad1-109">모드</span><span class="sxs-lookup"><span data-stu-id="c1ad1-109">Mode</span></span>  
 <span data-ttu-id="c1ad1-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="c1ad1-110">Data type: string</span></span>  
  
 <span data-ttu-id="c1ad1-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c1ad1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c1ad1-112">바인딩으로 구성된 끝점이 메시지 수준 보안을 사용하는지 또는 전송 수준 보안을 사용하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ad1-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="c1ad1-113">전송</span><span class="sxs-lookup"><span data-stu-id="c1ad1-113">Transport</span></span>  
 <span data-ttu-id="c1ad1-114">데이터 형식: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="c1ad1-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="c1ad1-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c1ad1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c1ad1-116">전송 보안 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ad1-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ad1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1ad1-117">Requirements</span></span>  
  
|<span data-ttu-id="c1ad1-118">MOF</span><span class="sxs-lookup"><span data-stu-id="c1ad1-118">MOF</span></span>|<span data-ttu-id="c1ad1-119">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ad1-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c1ad1-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c1ad1-120">Namespace</span></span>|<span data-ttu-id="c1ad1-121">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ad1-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1ad1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1ad1-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
