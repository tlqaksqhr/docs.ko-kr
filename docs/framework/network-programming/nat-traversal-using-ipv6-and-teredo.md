---
title: "IPv6 및 Teredo를 사용하는 NAT 통과 | Microsoft Docs"
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
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# IPv6 및 Teredo를 사용하는 NAT 통과
향상 된 네트워크 주소 변환 \(NAT\) 통과 대 한 지원을 제공 했습니다.  이러한 변경 사항은 IPv6 및 Teredo를 사용 하도록 설계 되었지만 또한 다른 IP 터널링 기술을 적용할 수 있습니다.  이러한 향상 된 클래스에 영향을 주지는 <xref:System.Net> 와 관련 된 네임 스페이스입니다.  
  
 이러한 변경 사항은 IP 터널링 기술을 사용 하 여 클라이언트 및 서버 응용 프로그램에 영향을 줍니다.  
  
 NAT 통과 변경은.NET Framework 버전 4 사용 하 여 응용 프로그램에만 사용할 수 있습니다.  이러한 기능은 이전 버전의.NET Framework 사용할 수 있습니다.  
  
## 개요  
 인터넷 프로토콜 버전 4 \(IPv4\) IPv4 주소 32 비트 수를 정의 합니다.  결과적으로 약 4 억 개의 고유한 IP 주소를 i p v 4를 지원 \(2 ^32\).  컴퓨터 및 네트워크 장치에서 확장 1990 년대 인터넷의 숫자로 제한 IPv4 주소 공간의 명백해.  
  
 I p v 4의 수명을 연장 하는 데 사용 되는 몇 가지 방법 중 하나로 했습니다 많은 개인 IP 나타내는 하나의 고유한 공용 IP 주소를 허용 하려면 NAT 배포할 주소 \(개인 인트라넷\).  NAT 장치 뒤의 개인 IP 주소를 단일 공용 IPv4 주소를 공유합니다.  NAT 장치는 저렴 한 무선 액세스 포인트와 라우터를 사용 하는 전용된 하드웨어 장치 또는 NAT.를 제공 하는 서비스를 실행 하는 컴퓨터 수 있습니다.  장치 또는 서비스를이 공용 IP 주소에 대 한 공용 인터넷 및 개인 인트라넷 사이 IP 네트워크 패킷을 변환합니다.  
  
 이 구성표 다른 IP 주소 \(일반적으로 서버\) 인터넷에 요청을 보내는 개인 인트라넷에서 실행 및 클라이언트 응용 프로그램에 사용할 수 있습니다.  응답을 보낼 위치를 알 수 있는 응답이 반환 될 때 NAT 장치 또는 서버 클라이언트 요청의 매핑을 그렇게 유지할 수 있습니다.  하지만이 체계 서비스 제공, 패킷에 대 한 수신 대기 및 응답 하려는 NAT 장치 뒤의 개인 인트라넷에서 실행 중인 응용 프로그램에 대 한 문제를 초래 합니다.  이 경우 특히 피어\-투\-피어 응용 프로그램입니다.  
  
 IPv6 프로토콜은 IPv4 주소 128 비트 수를 정의합니다.  결과적으로 IPv6 3.2 x 10은 매우 큰 IP 주소 공간을 지원 ^38 고유 주소 \(2 ^128\).  이 크기는 주소 공간을 고유 주소를 인터넷에 연결 된 모든 장치에 대해 가능 합니다.  하지만 문제가 있습니다.  세계의 많은 여전히 i p v 4만 사용 합니다.  특히 많은 기존 라우터 및 소규모 회사, 조직 및 가정에서 사용 되는 무선 액세스 포인트 IPv6 지원 하지 않습니다.  또한 이러한 고객 지원 일부 인터넷 서비스 공급자 지원 하지 않는 또는 i p v 6에 대 한 지원을 구성 하지 않았습니다.  
  
 터널 IPv6 주소는 IPv4 패킷에 여러 IPv6 전환 기술은 개발 되었습니다.  6To4, ISATAP, 이러한 기술을 포함 하 고 Teredo IPv6 호스트 IP4 네트워크 다른 IPv6 네트워크에 도달 하기 위해 통과 해야 하는 경우 유니캐스트 IPv6 트래픽에 주소 할당 및 호스트 간 자동 터널링을 제공는 터널.  IPv6 패킷은 IPv4 패킷으로 터널링 된 보내집니다.  NAT 장치를 통해 IPv6 주소의 NAT 통과 허용 하는 여러 가지 터널링 기술은 사용 중인입니다.  
  
 Teredo IPv4 네트워크에 IPv6 연결을 제공 하는 IPv6 전환 기술 중 하나입니다.  Teredo 인터넷 엔지니어링 작업 강제 \(IETF에서\) 게시 4380 RFC에에서 설명 되어 있습니다.  Windows XP SP2 및 나중에 공용 IPv6 주소 범위 2001:0에서 제공 하는 가상 Teredo 어댑터 지원:: \/ 32.  이 IPv6 주소는 인터넷에서 들어오는 연결에 대해 수신 대기를 사용할 수 있습니다 및 수신 대기 서비스에 연결 하려면 IPv6 가능 클라이언트에 제공할 수 있습니다.  이 응용 프로그램에서 바로 응용 프로그램의 Teredo IPv6 주소를 사용 하 여 연결할 수 있으므로 NAT 장치 뒤에 있는 컴퓨터 해결 방법에 대 한 염려 해제 합니다.  
  
## 향상 된 지원 NAT 통과 및 Teredo  
 향상 된 추가 되는 <xref:System.Net>, <xref:System.Net.NetworkInformation>, 및 <xref:System.Net.Sockets> Teredo 및 i p v 6을 사용 하 여 NAT 통과 지원에 대 한 네임 스페이스.  
  
 몇 가지 방법을 추가 <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=fullName> 유니캐스트 목록을 호스트에서 IP 주소를 얻을 수 있는 클래스입니다.  <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> 메서드 로컬 컴퓨터의 안정 된 유니캐스트 IP 주소 테이블을 검색 하는 비동기 요청을 시작 합니다.  <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> 메서드는 로컬 컴퓨터의 안정 된 유니캐스트 IP 주소 테이블을 검색 하는 보류 중인 비동기 요청을 끝냅니다.  <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> 메서드는 동기 요청 주소 테이블에 필요한 경우 일정 해질 때까지 대기 하는 로컬 컴퓨터의 안정 된 유니캐스트 IP 주소 테이블을 검색 합니다.  
  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName> 속성을 사용 하 여 확인 하는 <xref:System.Net.IPAddress> Teredo IPv6 주소입니다.  
  
 이러한 새로운 사용 하 여 <xref:System.Net.NetworkInformation.IPGlobalProperties> 클래스와 함께에서 메서드를 <xref:System.Net.IPAddress.IsIPv6Teredo%2A> 속성을 응용 프로그램 Teredo 주소를 쉽게 찾을 수 있습니다.  신청서만 일반적으로이 정보를 원격 응용 프로그램에 통신 하 고 있으면 로컬 Teredo 주소를 알 필요가 있습니다.  예를 들어, 피어\-투\-피어 응용 프로그램은 모든 IPv6 주소는 다음 다른 사람에 게 전달할 수 있는 매치 메이크 서버 피어 직접 통신할 수 있도록 보낼 수 있습니다.  
  
 응용 프로그램을 정상적으로 수신 하는 수신 서비스 설정 해야 <xref:System.Net.IPAddress.IPv6Any?displayProperty=fullName> Teredo 주소를 로컬이 아닌.  원격 클라이언트 또는 피어 호스트의 수신 서비스를 직접 IPv6 경로 경우 클라이언트나 피어 i p v 6을 사용 하 여 직접 연결 Teredo 터널 패킷을 사용 하지 않아도 수 있습니다.  
  
 TCP 응용 프로그램에 <xref:System.Net.Sockets.TcpListener?displayProperty=fullName> 클래스에는 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> NAT 통과 메서드.  UDP 응용 프로그램을 <xref:System.Net.Sockets.UdpClient?displayProperty=fullName> 클래스에는 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> NAT 통과 메서드.  
  
 사용 하는 응용 프로그램의 <xref:System.Net.Sockets.Socket?displayProperty=fullName> 및 관련된 클래스는 <xref:System.Net.Sockets.Socket.GetSocketOption%2A> 및 <xref:System.Net.Sockets.Socket.SetSocketOption%2A> 메서드를 사용할 수는 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> 소켓 옵션 설정 또는 해제 NAT 통과 쿼리를.  
  
## 참고 항목  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=fullName>