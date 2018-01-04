---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d737a7334098961cccb73a114be9be5bb71727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a>202 - ClientMessageInspectorBeforeSendInvoked
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|202|  
|키워드|문제 해결, ServiceModel|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 이 이벤트는 서비스 모델이 클라이언트 메시지 검사자에 대해 `BeforeSendRequest` 메서드를 호출한 후에 내보내집니다.  
  
## <a name="message"></a>메시지  
 디스패처가 '%1' 형식의 ClientMessageInspector에 대해 'BeforeSendRequest'를 호출했습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|호출된 검사자 형식의 CLR FullName입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'. 예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
