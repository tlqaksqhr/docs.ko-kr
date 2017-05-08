---
title: "Calls Faulted Per Second | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Calls Faulted Per Second
카운터 이름: Calls Faulted Per Second  
  
## 설명  
 초당 이 작업에 오류를 반환한 호출의 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)로 되어 있습니다. 이 형식의 값은 다음과 같은 수식으로 계산됩니다.  
  
 \(N 1 \- N 0 \) \/ \( \(D 1 \-D 0 \) \/ F\)  
  
 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 응용 프로그램에서 서비스 메서드는 SOAP 오류 메시지를 사용하여 처리 오류 정보를 전달합니다.SOAP 오류는 서비스 작업의 메타데이터에 포함된 메시지 유형이므로 클라이언트가 실행을 더욱 견고하게 만들거나 대화형으로 만드는 데 사용할 수 있는 오류 계약을 만듭니다.SOAP 오류는 XML 형식으로 클라이언트에 표현되므로 상호 운용성이 매우 높습니다.  
  
## 참고 항목  
 [계약 및 서비스에서 오류 지정 및 처리](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)