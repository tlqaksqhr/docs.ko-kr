---
title: 1040 - InArgumentBound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b3ce0997dcdad4779f87744edf661316b2efa47c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1040---inargumentbound"></a>1040 - InArgumentBound
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1040|  
|키워드|WFActivities|  
|수준|Verbose|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 In Argument가 바인딩되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 작업 '%2', DisplayName: '%3', InstanceId: '%4'에 대한 In Argument '%1'이(가) 값: %5에 바인딩되었습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|InArgument|xs:string|InArgument의 이름입니다.|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|값|xs:string|InArgument에 바인딩된 값입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
