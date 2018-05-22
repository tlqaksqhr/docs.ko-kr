---
title: 인터넷 프로토콜 버전 6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 995bc2075a7df5c9a37cc68e812f62c9de2e53c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="internet-protocol-version-6"></a>인터넷 프로토콜 버전 6
IPv6(인터넷 프로토콜 버전 6)은 인터넷 네트워크 계층에 대한 새로운 표준 프로토콜 도구 모음입니다. IPv6은 주소 고갈, 보안, 자동 구성, 확장성 등에 관련된 현재 버전 인터넷 프로토콜 도구 모음(IPv4라고 함)의 많은 문제를 해결하도록 설계되었습니다. IPv6은 피어 투 피어 및 모바일 응용 프로그램을 포함한 새로운 종류의 응용 프로그램을 구현하기 위해 인터넷 기능을 확장합니다. 현재 IPv4 프로토콜의 주요 문제는 다음과 같습니다.  
  
-   주소 공간의 빠른 고갈.  
  
     이 문제로 인해 여러 개인 주소를 단일 공용 IP 주소에 매핑하는 NAT(Network Address Translator)를 사용하게 됩니다. 이 메커니즘에서 발생하는 주요 문제는 처리 오버헤드 및 종단 간 연결 부족입니다.  
  
-   계층 구조 지원 없음.  
  
     고유의 미리 정의된 클래스 조직으로 인해 IPv4에는 실제 계층 구조 지원이 없습니다. 실제로 네트워크 토폴로지를 매핑하는 방식으로 IP 주소를 구조화할 수는 없습니다. 이 중대한 설계 결함으로 인해 IPv4 패킷을 인터넷의 임의 위치에 전달하기 위해 큰 라우팅 테이블이 필요하게 되었습니다.  
  
-   복잡한 네트워크 구성.  
  
     IPv4를 사용할 경우 주소를 정적으로 할당하거나 주소에 DHCP 등의 구성 프로토콜을 사용 중이어야 합니다. 이상적인 상황에서는 호스트가 DHCP 인프라의 관리에 의존할 필요가 없습니다. 대신에 호스트는 배치되어 있는 네트워크 세그먼트를 기반으로 구성될 수 있습니다.  
  
-   기본 제공 인증 및 기밀성 없음.  
  
     IPv4의 경우 교환된 데이터에 대한 인증이나 암호화를 제공하는 메커니즘을 지원할 필요가 없습니다. 이 내용은 IPv6에서 변경됩니다. IPSec(인터넷 프로토콜 보안)는 IPv6 지원 요구 사항입니다.  
  
 새로운 프로토콜 도구 모음은 다음 기본 요구 사항을 충족해야 합니다.  
  
-   낮은 오버헤드가 발생하는 대규모 라우팅 및 주소 지정.  
  
-   다양한 연결 상황에 대한 자동 구성.  
  
-   기본 제공 인증 및 기밀성.  
  
 자세한 내용은 [IPv6 주소 지정](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6 라우팅](../../../docs/framework/network-programming/ipv6-routing.md), [IPv6 자동 구성](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [IPv6 사용 및 사용 안 함](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) 및 [방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)을 참조하세요.  
  
## <a name="references"></a>참조  
 Internet Engineering Task Force 사이트([http://www.ietf.org](http://www.ietf.org/))에서 찾을 수 있는 선택된 RFC 문서는 다음과 같습니다.  
  
-   RFC 1287, Towards the Future Internet Architecture.  
  
-   RFC 1454, Comparison of Proposals for Next Version of IP.  
  
-   RFC 2373, IP Version 6 Addressing Architecture.  
  
-   RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.  
  
 또한 [Technet의 IPv6 영역](http://go.microsoft.com/fwlink/?LinkID=179658)에서 IPv6 관련 정보를 찾을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPv6 소켓 샘플](http://go.microsoft.com/fwlink/?LinkID=179568)  
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)  
 [소켓](../../../docs/framework/network-programming/sockets.md)
