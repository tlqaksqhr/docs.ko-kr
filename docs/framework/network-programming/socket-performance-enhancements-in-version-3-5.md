---
title: "버전 3.5의 소켓 성능 향상 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 버전 3.5의 소켓 성능 향상
<xref:System.Net.Sockets.Socket?displayProperty=fullName> 클래스 최고의 성능을 달성 하기 위해 비동기 네트워크 I\/O를 사용 하는 응용 프로그램에서 향상 버전 3.5 사용 했습니다 되었습니다 있습니다.  일련의 새 클래스의 향상 된 기능 집합의 일부로 추가 되었습니다의 <xref:System.Net.Sockets.Socket> 클래스는 특수 고성능 소켓 응용 프로그램에서 사용할 수 있는 대체 비동기 패턴을 제공 합니다.  이러한 향상 된이 기능은 특히 고성능을 필요로 하는 네트워크 서버 응용 프로그램에 대 한 설계 되었습니다.  응용 프로그램은 향상 된 비동기 패턴을 단독으로 사용할 수 있습니다에 \(예를 들어 많은 양의 데이터를 수신 하는 경우\) 응용 프로그램의 영역을 대상.  
  
## 클래스 향상  
 향상된 비동기 패턴의 주 기능은 대용량 비동기 소켓 I\/O 작업을 실행하는 동안 개체를 반복적으로 할당하고 동기화하지 않는 것입니다.  현재 구현 시작\/종료 디자인 패턴은 <xref:System.Net.Sockets.Socket> 비동기 소켓 I\/O 요구에 대 한 클래스는 <xref:System.IAsyncResult?displayProperty=fullName> 각 비동기 소켓 작업에 할당할 개체.  
  
 새로 <xref:System.Net.Sockets.Socket> 향상 된 비동기 소켓 작업에 다시 사용할 수 있는 설명 되어 클래스 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName> 클래스 개체를 할당 하 고 응용 프로그램에서 유지 관리 합니다.  고성능 소켓 응용 프로그램에서는 유지해야 할 중첩된 소켓 작업의 양을 가장 잘 압니다.  응용 프로그램에서는 <xref:System.Net.Sockets.SocketAsyncEventArgs> 개체를 필요한 만큼 만들 수 있습니다.  서버 응용 프로그램 15 소켓 처리 되지 않은 작업 항상 들어오는 클라이언트 연결 속도 지원 하기 위해 적용 해야 하는 경우 예를 들어,이 15 다시 할당할 수 <xref:System.Net.Sockets.SocketAsyncEventArgs> 미리 그 목적에 대 한 개체.  
  
 이 클래스를 사용하여 비동기 소켓 작업을 수행하는 패턴은 다음과 같은 단계로 구성됩니다.  
  
1.  <xref:System.Net.Sockets.SocketAsyncEventArgs> 컨텍스트 개체를 새로 할당하거나 응용 프로그램 풀에서 가져옵니다.  
  
2.  컨텍스트 속성 설정 작업에 대 한 \(콜백 대리자 메서드 및 데이터 버퍼를 예를 들어\)에 수행 개체입니다.  
  
3.  적절한 소켓 메서드\(xxxAsync\)를 호출하여 비동기 작업을 시작합니다.  
  
4.  비동기 소켓 메서드 \(xxxAsync\) 콜백에서 true를 반환 하면 컨텍스트 속성에 대 한 완료 상태를 쿼리 합니다.  
  
5.  비동기 소켓 메서드 \(xxxAsync\) 콜백을 동기적으로 완료 된 작업에서 false를 반환 하는 경우.  이 경우에는 컨텍스트 속성을 쿼리하여 작업 결과를 확인할 수 있습니다.  
  
6.  컨텍스트를 다른 작업에 다시 사용하고 풀에 다시 배치하거나 삭제합니다.  
  
 새 비동기 소켓 작업 컨텍스트 개체의 수명은 응용 프로그램 코드에서 참조 및 비동기 I\/O 참조에 의해 결정 됩니다.  비동기 소켓 작업 컨텍스트 개체가 비동기 소켓 작업 메서드 중 하나에 매개 변수로 제출된 후에는 응용 프로그램에서 이 개체에 대한 참조를 유지할 필요가 없습니다.  이 개체는 완료 콜백이 반환될 때까지 계속 참조됩니다.  그러나 이후 비동기 소켓 작업에 다시 사용할 수 있도록 컨텍스트 개체의 참조를 유지 하는 응용 프로그램의 장점입니다.  
  
## 참고 항목  
 <xref:System.Net.Sockets.Socket?displayProperty=fullName>   
 <xref:System.Net.Sockets.SendPacketsElement?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=fullName>   
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)   
 [소켓 성능 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179570)