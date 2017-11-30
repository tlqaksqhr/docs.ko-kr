---
title: "연결 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Internet, connections
- connections [.NET Framework], grouping
- WebRequest class, connection grouping
- network resources, connections
- connection pooling
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b947051d809d5e8f5be3410b269c872bfc108ec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="connection-grouping"></a>연결 그룹화
연결 그룹화는 단일 응용 프로그램 내의 특정 요청을 정의된 연결 풀에 연결합니다. 이 기능은 사용자 대신 백 엔드 서버에 연결되고 Kerberos와 같은 위임을 지원하는 인증 프로토콜을 사용하는 중간 계층 응용 프로그램에 필요하거나 다음 예제와 같이 자체적인 자격 증명을 제공하는 중간 계층 응용 프로그램에 필요할 수 있습니다. 예를 들어 사용자인 Joe가 급여 정보를 표시하는 내부 웹 사이트를 방문한다고 가정합니다. Joe를 인증한 후 중간 계층 응용 프로그램 서버는 Joe의 자격 증명을 사용하여 백 엔드 서버에 연결하고 급여 정보를 검색합니다. 다음으로 Susan은 사이트를 방문하고 급여 정보를 요청합니다. 중간 계층 응용 프로그램은 Joe의 자격 증명으로 이미 연결을 설정했으므로 백 엔드 서버는 Joe의 정보를 표시합니다. 그러나 응용 프로그램이 백 엔드 서버로 보낸 각 요청을 사용자 이름에서 형성된 연결 그룹에 할당하면 각 사용자는 개별 연결 풀에 속하고 실수로 다른 사용자와 인증 정보를 공유할 수 없습니다.  
  
 요청을 특정 연결 그룹에 할당하려면 요청을 만들기 전에 <xref:System.Net.WebRequest>의 <xref:System.Net.WebRequest.ConnectionGroupName%2A> 속성에 이름을 할당해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연결 관리](../../../docs/framework/network-programming/managing-connections.md)  
 [방법: 그룹 연결에 사용자 정보 할당](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)
