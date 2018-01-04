---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1031|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 FaultWorkItem이 완료되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|오류 작업의 형식 이름입니다.|  
|FaultActivityDisplayName|xs:string|오류 작업의 표시 이름입니다.|  
|FaultActivityInstanceId|xs:string|오류 작업의 인스턴스 ID입니다.|  
|ExceptionActivity|xs:string|예외를 throw한 작업의 형식 이름입니다.|  
|ExceptionActivityDisplayName|xs:string|예외를 throw한 작업의 표시 이름입니다.|  
|ExceptionActivityInstanceId|xs:string|예외를 throw한 작업의 인스턴스 ID입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
