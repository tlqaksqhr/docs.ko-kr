---
title: "IPv6 사용 및 사용 안 함 | Microsoft Docs"
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
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# IPv6 사용 및 사용 안 함
IPv6 프로토콜을 사용 하려면 i p v 6을 지 원하는 운영 체제 버전이 실행 되 고 있는지 확인 및 운영 체제 및 네트워킹 클래스가 올바르게 구성 되었는지 확인 합니다.  
  
## 구성 단계  
 다음 표에서 다양 한 구성  
  
|운영 체제 IPv6 가능?|네트워킹\-IPv6 가능 클래스?|설명|  
|--------------------|------------------------|--------|  
|아니요|아니요|IPv6 주소를 구문 분석할 수 있습니다.|  
|아니요|예|IPv6 주소를 구문 분석할 수 있습니다.|  
|예|아니요|IPv6 주소를 구문 분석 하 고 IPv6 주소를 일으키지 않는 이름 확인 방법을 사용 하 여 있습니다.|  
|예|예|구문 분석 하 고 일으키지 포함 하 여 모든 메서드를 사용 하 여 IPv6 주소를 확인할 수 있습니다.|  
  
 System.Net 네임 스페이스의 모든 클래스에 대 한 IPv6 지원을 사용 하 여 응용 프로그램의 구성 파일 또는 컴퓨터 구성 파일 수정 해야 유의 하십시오.  구성 파일은 응용 프로그램에 대 한 컴퓨터 구성 파일을 통해 우선 순위를 가집니다.  
  
 컴퓨터 구성 파일을 수정 하는 방법의 예  *machine.config*, Ipv6 지원 참조를 사용할 수 있도록  [방법: Ipv6 사용을 지원 하도록 컴퓨터 구성 파일 수정](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  또한 IPv6 지원 운영 체제에 설정 되었는지 확인 합니다.  
  
 .NET Framework 구성 파일에 다음과 같이 설정 하는 구성 스위치가 있는 경우  
  
```  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 .NET Framework 버전 1.1이 하에서의 값에 대 한는 **ipv6 enabled** 구성 스위치를 지정 여부의 멤버는 <xref:System.Net.Dns?displayProperty=fullName> 클래스 IPv6 주소를 반환 합니다.  
  
 .NET Framework 버전 2.0 및 이후 Windows IPv6 다음 멤버를 지 원하는 경우에 <xref:System.Net.Dns?displayProperty=fullName> 클래스 \(예를 들어,는 <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName> 메서드\)를 한 가지 제한 사항은 IPv6 주소를 반환 합니다.  구성원의 DNS 사용 하지 않는 <xref:System.Net.Dns?displayProperty=fullName> \(예를 들어 있는 <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName> 메서드\) 읽고 사용 하는 ipv6 설정에 대 한 구성 파일의 값을 인식 합니다.  
  
## 참고 항목  
 [인터넷 프로토콜 버전 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [소켓](../../../docs/framework/network-programming/sockets.md)   
 [네트워크 설정 스키마](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)