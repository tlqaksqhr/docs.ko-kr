---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512296"
---
# <a name="1126---invokedmethodthrewexception"></a>1126 - InvokedMethodThrewException
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1126|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다. %2  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|InvokeMethod 작업의 표시 이름입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
