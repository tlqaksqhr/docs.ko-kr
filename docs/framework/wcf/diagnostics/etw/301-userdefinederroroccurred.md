---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d54930a29a24dab97ce403c2808fb74b8cbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="301---userdefinederroroccurred"></a>301 - UserDefinedErrorOccurred
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|301|  
|키워드|문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|수준|오류|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 이 이벤트는 사용자 코드에서 내보내집니다. 개발자는 자신의 서비스에서 사용자 정의 오류가 발생할 때 이 이벤트를 내보낼 수 있습니다. 이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다. 이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.  
  
## <a name="message"></a>메시지  
 이름:'%1', 참조:'%2', 페이로드:%3  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|name|`xs:string`|이벤트의 사용자 정의 이름입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'. 예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.|  
|Payload|`xs:string`|이벤트의 사용자 정의 페이로드입니다.|
