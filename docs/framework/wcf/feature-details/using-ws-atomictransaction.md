---
title: WS-AtomicTransaction 사용
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 7880d46d4827b36c7806c61877edf79faa766371
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498259"
---
# <a name="using-ws-atomictransaction"></a>WS-AtomicTransaction 사용
WS-AT(WS-AtomicTransaction)는 상호 운용 가능 트랜잭션 프로토콜입니다. 이 프로토콜을 사용하면 웹 서비스 메시지를 통해 분산 트랜잭션 흐름을 만들 수 있고 유형이 다른 트랜잭션 인프라 간에 상호 운용이 가능한 방식으로 이를 조정할 수 있습니다. 그리고 WS-AT에서는 2단계의 커밋 프로토콜을 사용하여 분산 응용 프로그램, 트랜잭션 관리자 및 리소스 관리자 간의 원자 단위 결과를 도출합니다.  
  
 Microsoft Distributed Transaction Coordinator (MSDTC) 트랜잭션 관리자에 기본 제공 되는 프로토콜 서비스를 포함 하는 Windows Communication Foundation (WCF)를 제공 하는 WS-AT 구현 합니다. WCF 응용 프로그램은 WS-AT를 사용 하면 타사 기술을 사용 하 여 작성 된 상호 운용 가능 웹 서비스를 포함 하 여 다른 응용 프로그램에 트랜잭션을 게 전달할 수 있습니다.  
  
 클라이언트 응용 프로그램과 서버 응용 프로그램 간에 트랜잭션이 진행될 때, 사용되는 트랜잭션 프로토콜은 클라이언트에서 선택한 끝점에서 서버를 통해 노출된 바인딩에 의해 결정됩니다. 일부 WCF 시스템 제공 바인딩은 기본을 지정 하는 `OleTransactions` 다른 ws-at 기본값으로 사용 하는 동안 트랜잭션 전파 형식으로 프로토콜입니다. 제공된 바인딩 내의 트랜잭션 프로토콜 선택은 프로그래밍 방식으로 수정할 수도 있습니다.  
  
 프로토콜 선택에 따라 다음 사항이 결정됩니다.  
  
-   클라이언트에서 서버로 트랜잭션을 하는 데 사용되는 메시지 헤더의 형식  
  
-   트랜잭션 결과를 확인하기 위해 클라이언트의 트랜잭션 관리자와 서버의 트랜잭션 사이에서 2단계 커밋 프로토콜을 실행하는 데 사용되는 네트워크 프로토콜  
  
 서버와 클라이언트는를 작성 한 경우 WCF를 사용 하 여 WS-AT를 사용할 필요가 없습니다. 대신 활성화된 `NetTcpBinding` 특성을 가진 `TransactionFlow`의 기본 설정을 사용할 수 있습니다. 여기에는 `OleTransactions` 프로토콜이 대신 사용됩니다. 자세한 내용은 참조 [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)합니다. 타사 기술을 기반으로 구축한 웹 서비스로 트랜잭션을 이동하는 경우에는 WS-AT를 사용해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WS-Atomic Transaction 지원 구성](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
