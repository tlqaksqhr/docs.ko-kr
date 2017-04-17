---
title: "NetworkInformation | Microsoft Docs"
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
helpviewer_keywords: 
  - "네트워크"
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# NetworkInformation
<xref:System.Net.NetworkInformation> 네임 스페이스를 사용 하 여 네트워크 이벤트, 변경, 통계 및 속성에 대 한 정보를 수집 합니다.  사용 하 여 원격 호스트에 연결할 수 있는지 확인할 수 있는 <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> 클래스입니다.  
  
## 네트워크 가용성 및 이벤트  
 <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=fullName> 클래스를 사용 하면 네트워크 주소 또는 가용성 변경 되었는지 여부를 확인 합니다.  이 클래스를 사용 하는 변경 내용을 처리 하기 위해 이벤트 처리기 만들기 및 연관 된 <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> 또는 <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>.  자세한 내용은 [방법: 네트워크 가용성 및 주소 변경 검색](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md)을 참조하십시오.  
  
## 네트워크 통계 및 속성  
 인터페이스 또는 프로토콜 별로 네트워크 통계 및 속성을 수집할 수 있습니다.  <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType>, 및 <xref:System.Net.NetworkInformation.PhysicalAddress> 클래스는 특정 네트워크 인터페이스에 대 한 정보를 제공 하지만 <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics>, 및 <xref:System.Net.NetworkInformation.UdpStatistics> 클래스 계층 3에 대 한 정보를 제공 하며 4 패킷 계층.  자세한 내용은 [방법: 인터페이스 및 프로토콜 정보 가져오기](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md)을 참조하십시오.  
  
## 원격 호스트 Reachable 인지 확인  
 사용할 수 있는 <xref:System.Net.NetworkInformation.Ping> 원격 호스트를, 네트워크와 연결할 수 있는지 여부를 확인 하는 클래스.  자세한 내용은 [방법: 호스트 Ping](../../../docs/framework/network-programming/how-to-ping-a-host.md)을 참조하십시오.  
  
## 참고 항목  
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)   
 [네트워크 정보 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179564)   
 [NetStat 도구 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179562)   
 [Ping 클라이언트 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179565)