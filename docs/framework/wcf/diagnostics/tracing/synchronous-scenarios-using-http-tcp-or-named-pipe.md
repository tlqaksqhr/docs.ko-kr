---
title: "HTTP, TCP 또는 명명된 파이프를 사용하는 동기 시나리오 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# HTTP, TCP 또는 명명된 파이프를 사용하는 동기 시나리오
이 항목에서는 HTTP, TCP 또는 명명된 파이프를 사용하는 단일 스레드 클라이언트가 포함된 다양한 동기 요청\/회신 시나리오의 작업 및 전송에 대해 설명합니다.다중 스레드 요청에 대한 자세한 내용은 [HTTP, TCP 또는 명명된 파이프를 사용하는 비동기 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/asynchronous-scenarios-using-http-tcp-or-named-pipe.md)를 참조하십시오.  
  
## 오류가 없는 동기 요청\/회신  
 이 단원에서는 단일 스레드 클라이언트에서의 유효한 동기 요청\/회신 시나리오 작업 및 전송에 대해 설명합니다.  
  
### 클라이언트  
  
#### 서비스 끝점과의 통신 설정  
 클라이언트가 구성되고 열립니다.이러한 각 단계에서 앰비언트 동작\(A\)은 “Construct Client” 동작\(B\)과 “Open Client” 동작\(C\)으로 각각 전송됩니다.전송 중인 각 동작에서 앰비언트 동작은 다시 전송될 때까지, 즉 ServiceModel 코드가 실행될 때까지 일시 중단됩니다.  
  
#### 서비스 끝점에 요청하기  
 앰비언트 동작은 “ProcessAction” 동작\(D\)으로 전송됩니다.이 동작 내에서 요청 메시지가 전송되고 응답 메시지가 수신됩니다.이 동작은 컨트롤이 사용자 코드로 반환되면 종료됩니다.이것은 동기 요청이므로 컨트롤이 반환될 때까지 앰비언트 동작이 일시 중단됩니다.  
  
#### 서비스 끝점과의 통신 닫기  
 클라이언트의 닫기 동작\(I\)은 앰비언트 동작에서 만들어집니다.이 동작은 새로 만들기 및 열기와 동일합니다.  
  
### 서버  
  
#### 서비스 호스트 설정  
 ServiceHost의 새로 만들기 및 열기 동작\(N 및 O\)은 앰비언트 동작\(M\)에서 만들어집니다.  
  
 수신기 동작\(P\)은 각 수신기의 ServiceHost를 열면 만들어집니다.수신기 동작은 데이터를 받고 처리할 때까지 기다립니다.  
  
#### 통신 중에 데이터 받기  
 데이터가 연결되면 받은 데이터를 처리할 동작\(Q\)이 없는 경우 “ReceiveBytes” 동작이 만들어집니다.이 동작은 연결 또는 큐 내의 여러 메시지에 다시 사용할 수 있습니다.  
  
 ReceiveBytes 동작은 SOAP 동작 메시지를 구성할 데이터가 충분하면 ProcessMessage 동작\(R\)을 시작합니다.  
  
 동작 R에서 메시지 헤더가 처리되고 activityID 헤더가 확인됩니다.이 헤더가 있는 경우 동작 ID는 ProcessAction 동작으로 설정되고 그렇지 않으면, 새 ID가 만들어집니다.  
  
 ProcessAction 동작\(S\)이 만들어지고 호출이 처리되면 전송됩니다.이 동작은 사용자 코드\(T\) 실행 및 가능한 경우 응답 메시지 보내기를 비롯하여 들어오는 메시지와 관련된 모든 처리가 완료되면 종료됩니다.  
  
#### 서비스 호스트 닫기  
 ServiceHost의 닫기 동작\(Z\)은 앰비언트 동작에서 만들어집니다.  
  
 ![HTTP&#47;TCP&#47;명명된 파이프를 사용하는 동기 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/media/sync.gif "Sync")  
  
 \<A: name\>에서 `A`는 이전 텍스트 및 표 3의 동작을 설명하는 바로 가기 기호입니다.`Name`은 동작의 약식 이름입니다.  
  
 `propagateActivity`\=`true`인 경우 클라이언트와 서비스에 대한 작업 처리의 동작 ID가 같습니다.  
  
## 오류가 있는 동기 요청\/회신  
 이전 시나리오와 유일하게 다른 점은 SOAP 오류 메시지가 응답 메시지로 반환된다는 것입니다.`propagateActivity`\=`true`인 경우 요청 메시지의 동작 ID가 SOAP 오류 메시지에 추가됩니다.  
  
## 오류가 없는 동기 단방향  
 첫 번째 시나리오와 유일하게 다른 점은 메시지가 서버로 반환되지 않는다는 것입니다.HTTP 기반 프로토콜의 경우 상태\(유효 또는 오류\)가 클라이언트로 반환됩니다.HTTP가 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 프로토콜 스택의 일부인 요청 응답 의미 체계가 있는 유일한 프로토콜이기 때문입니다.TCP 처리는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 표시되지 않으므로 클라이언트에게 확인 메시지가 발송되지 않습니다.  
  
## 오류가 있는 동기 단방향  
 메시지\(Q 이상\)를 처리하는 동안 오류가 발생하는 경우 클라이언트에게 확인 메시지가 반환되지 않습니다.이 시나리오는 "오류가 없는 동기 단방향" 시나리오와 동일합니다.오류 메시지를 받으려면 단방향 시나리오를 사용하지 마십시오.  
  
## 이중  
 이전 시나리오와 다른 점은 클라이언트가 서비스 역할을 한다는 것입니다. 여기서는 비동기 시나리오와 비슷한 ReceiveBytes 및 ProcessMessage 동작을 만듭니다.