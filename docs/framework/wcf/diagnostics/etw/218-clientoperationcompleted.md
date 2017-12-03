---
title: 218 - ClientOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d5b6fcc1c7ec4dd2f2c008e9d8bcfb58b2b4991
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="218---clientoperationcompleted"></a>218 - ClientOperationCompleted
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|218|  
|키워드가|문제 해결, ServiceModel|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 이 이벤트는 작업이 완료된 직후에 클라이언트에서 내보내집니다. 즉, 단방향 작업의 경우 메시지가 성공적으로 보내진 직후에 내보내지고 요청-응답 작업의 경우 응답이 수신된 후에 내보내집니다.  
  
## <a name="message"></a>메시지  
 클라이언트가 '%2' 계약과 연결된 '%1' 작업 실행을 완료했습니다. 메시지가 '%3'(으)로 전송되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|작업|xs:string|보내는 메시지의 SOAP 동작 헤더입니다.|  
|Contract Name|`xs:string`|계약 이름입니다. 예를 들면 ICalculator와 같습니다.|  
|대상|`xs:string`|메시지를 받은 서비스 끝점의 주소입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'. 예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
