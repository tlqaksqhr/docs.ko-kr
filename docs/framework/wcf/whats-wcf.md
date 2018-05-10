---
title: Windows Communication Foundation 정의
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
ms.openlocfilehash: e49b393b9dd09a513066a6cb3612ad9f938e9adb
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="what-is-windows-communication-foundation"></a>Windows Communication Foundation 정의
Windows Communication Foundation (WCF)는 서비스 지향 응용 프로그램을 작성 하기 위한 프레임 워크. WCF를 사용 하 여 보낼 수 있습니다 데이터를 비동기 메시지로 서비스 끝점에서 간에. 서비스 끝점은 IIS에서 호스팅하는 계속 사용 가능한 서비스의 일부분일 수도 있고 응용 프로그램에서 호스팅되는 서비스일 수도 있습니다. 또한 끝점은 서비스 끝점에서 데이터를 요청하는 서비스의 클라이언트일 수 있습니다. 메시지는 XML로 전송되는 한 문자나 단어처럼 간단할 수도 있고 이진 데이터 스트림처럼 복잡할 수도 있습니다. 다음은 몇 가지 샘플 시나리오입니다.  
  
-   비즈니스 트랜잭션을 처리하는 보안 서비스  
  
-   트래픽 보고서 또는 기타 모니터링 서비스와 같은 최신 데이터를 다른 서비스에 제공하는 서비스  
  
-   두 사람이 실시간으로 통신하거나 데이터를 교환할 수 있도록 하는 채팅 서비스  
  
-   하나 이상의 서비스를 폴링해 데이터를 가져와서 논리적 프레젠테이션으로 표시하는 대시보드 응용 프로그램  
  
-   Windows Workflow Foundation을 사용하여 구현되는 워크플로를 WCF 서비스로 노출  
  
-   서비스를 폴링해 최신 데이터 피드를 가져오는 Silverlight 응용 프로그램  
  
 이러한 응용 프로그램을 만드는 WCF 도입 되기 전에 수는 있었지만, WCF 쉬워집니다 끝점을 어느 때 보다 복잡해졌습니다. 요약 하자면, WCF 웹 서비스와 웹 서비스 클라이언트를 만들 수는 관리 가능한 접근을 제공 하도록 설계 되었습니다.  
  
## <a name="features-of-wcf"></a>WCF의 기능  
 WCF에는 다음과 같은 기능 집합이 포함 되어 있습니다. 자세한 내용은 참조 [WCF 기능 정보](../../../docs/framework/wcf/feature-details/index.md)합니다.  
  
-   **서비스 지향성**  
  
     WS 표준을 사용 하 여 결과 한 가지 WCF 만들 수 있습니다는 *서비스 지향* 응용 프로그램입니다. SOA(서비스 지향 아키텍처) 방식에서는 웹 서비스를 사용하여 데이터를 보내고 받습니다. 이러한 서비스에서는 응용 프로그램이 서로 하드 코드되지 않고 느슨하게 결합된다는 장점이 있습니다. 느슨하게 결합된 관계란 필수 계약이 충족되는 한 모든 플랫폼에서 만들어지는 모든 클라이언트가 어떤 서비스에나 연결할 수 있는 관계입니다.  
  
-   **상호 운용성**  
  
     WCF 웹 서비스 상호 운용성을 위한 최신 업계 표준을 구현합니다. 지원 되는 표준에 대 한 자세한 내용은 참조 [상호 운용성 및 통합](../../../docs/framework/wcf/feature-details/interoperability-and-integration.md)합니다.  
  
-   **다양한 메시지 패턴**  
  
     메시지가 교환되는 패턴에는 여러 가지가 있습니다. 그 중에서 가장 일반적인 패턴인 요청/회신 패턴에서는 한 끝점에서 두 번째 끝점의 데이터를 요청합니다. 그러면 두 번째 끝점에서 회신을 합니다. 또한 단일 끝점에서 회신을 기대하지 않고 메시지를 보내는 단방향 메시지와 같은 패턴도 있습니다. 보다 복잡한 패턴인 이중 교환 패턴은 두 끝점이 하나의 연결을 설정하여 데이터를 주고 받는 것으로, 인스턴트 메시징 프로그램과 유사합니다. 다양 한 메시지 교환을 구현 하는 방법에 대 한 자세한 내용은 WCF를 사용 하 여 패턴 참조 [계약](../../../docs/framework/wcf/feature-details/contracts.md)합니다.  
  
-   **서비스 메타데이터**  
  
     WCF는 WSDL, XML 스키마, Ws-policy 등 업계 표준으로 지정 된 형식을 사용 하 여 서비스 메타 데이터 게시를 지원 합니다. 자동으로 생성 하 고 WCF 서비스에 액세스 하기 위한 클라이언트를 구성 합니다.이 메타 데이터를 사용할 수 있습니다. 메타데이터는 HTTP 및 HTTPS를 통해 게시하거나 웹 서비스 메타데이터 교환 표준을 사용하여 게시할 수 있습니다. 자세한 내용은 참조 [메타 데이터](../../../docs/framework/wcf/feature-details/metadata.md)합니다.  
  
-   **데이터 계약**  
  
     사용 하 여 WCF은 빌드되므로 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], 코드에 적합 한 방식으로 적용할 계약을 제공 하는 포함 됩니다. 널리 사용되는 계약 유형 중 하나는 데이터 계약입니다. 기본적으로 Visual C# 또는 Visual Basic을 사용하여 서비스 코드를 작성할 때 데이터를 가장 쉽게 처리하는 방법은 데이터 엔터티에 속하는 속성을 사용하여 해당 데이터 엔터티를 나타내는 클래스를 만드는 것입니다. WCF에는 이와 같이 손쉬운 방식에서 데이터로 작업할 수 있는 포괄적인 시스템이 포함 되어 있습니다. 데이터를 나타내는 클래스를 만들면 서비스에서 메타데이터를 자동으로 생성하며, 이 메타데이터는 클라이언트가 사용자가 디자인한 데이터 형식을 준수할 수 있도록 합니다. 자세한 내용은 참조 [를 사용 하 여 데이터 계약](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
  
-   **보안**  
  
     개인 정보를 보호하기 위해 메시지를 암호화할 수 있으며, 사용자가 인증을 해야 메시지를 받을 수 있도록 지정할 수 있습니다. SSL 또는 WS-SecureConversation 등의 널리 알려진 표준을 사용하여 보안을 구현할 수 있습니다. 자세한 내용은 [보안](../../../docs/framework/wcf/feature-details/security.md)을 참조하세요.  
  
-   **다양한 전송 및 인코딩**  
  
     기본 제공되는 여러 전송 프로토콜 및 인코딩 중 원하는 항목을 사용하여 메시지를 전송할 수 있습니다. 가장 일반적인 프로토콜 및 인코딩 텍스트 인코딩된 하이퍼텍스트 전송 프로토콜 (HTTP)를 사용 하 여 World Wide Web에는 사용 하기 위해 SOAP 메시지를 보내기 위한 것입니다. 또는 WCF 파이프 또는 MSMQ를 명명 된 TCP를 통해 메시지를 보낼 수 있습니다. 이러한 메시지는 텍스트로 인코딩할 수도 있고 최적화된 이진 형식을 사용하여 인코딩할 수도 있습니다.  이진 데이터는 MTOM 표준을 사용하여 보내는 것이 효율적입니다. 제공되는 전송 또는 인코딩 중에서 요구 사항에 적합한 항목이 없는 경우에는 사용자 지정 전송 또는 인코딩을 직접 만들 수 있습니다. 전송 및 인코딩 WCF에서 지 원하는 방법에 대 한 자세한 내용은 참조 [전송](../../../docs/framework/wcf/feature-details/transports.md)합니다.  
  
-   **신뢰할 수 있는 메시지 및 대기 중인 메시지**  
  
     WCF는 Ws-reliable Messaging을 통해 구현 되 고 MSMQ를 사용 하 여 신뢰할 수 있는 세션을 사용 하 여 신뢰할 수 있는 메시지 교환을 지원 합니다. WCF에서 안정적이 고 큐에 대기 중인 메시징 지원에 대 한 자세한 내용은 참조 [큐 및 신뢰할 수 있는 세션](../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)합니다.  
  
-   **지속적 메시지**  
  
     지속적 메시지는 통신이 중단되어도 손실되지 않는 메시지입니다. 지속적 메시지 패턴의 메시지는 항상 데이터베이스에 저장됩니다. 통신이 중단되는 경우 연결이 복원되면 데이터베이스가 메시지 교환을 다시 시작할 수 있도록 해 줍니다. Windows WF (Workflow Foundation)를 사용 하 여 지속적 메시지를 만들 수 있습니다. 자세한 내용은 참조 [워크플로 서비스](../../../docs/framework/wcf/feature-details/workflow-services.md)합니다.  
  
-   **트랜잭션**  
  
     WCF는 WS-AtomicTtransactions, <xref:System.Transactions> 네임스페이스의 API 및 Microsoft Distributed Transaction Coordinator의 세 가지 트랜잭션 모델 중 하나를 사용하는 트랜잭션도 지원합니다. 트랜잭션에 대 한 자세한 내용은 wcf에서 지원 참조 [트랜잭션을](../../../docs/framework/wcf/feature-details/transactions-in-wcf.md)합니다.  
  
-   **AJAX 및 REST 지원**  
  
     REST는 Web 2.0 기술 발전에 대한 한 가지 예일 뿐입니다. WCF는 SOAP 봉투에 래핑되지 않은 "일반" XML 데이터 처리를 구성할 수 있습니다. WCF는 또한 ATOM (일반 RSS 표준), 및도 비-XML 형식, 같은 개체 JSON (JavaScript Notation) 등의 특정 XML 형식 지원 하도록 확장할 수 있습니다.  
  
-   **확장성**  
  
     WCF 아키텍처에 다양 한 확장성 지점입니다. 추가적인 기능이 필요한 경우에는 여러 진입점을 통해 서비스 동작을 사용자 지정할 수 있습니다. 사용 가능한 확장에 대 한 자세한 내용은 포인트 참조 [WCF 확장](../../../docs/framework/wcf/extending/index.md)합니다.  
  
## <a name="wcf-integration-with-other-microsoft-technologies"></a>WCF와 다른 Microsoft 기술의 통합  
 WCF는 유연한 플랫폼입니다. 이와 같이 뛰어난 유연성으로 인해 WCF 다른 여러 Microsoft 제품에도 사용 됩니다. WCF의 기초를 이해 하면 이러한 제품 사용 하는 경우 즉시 장점이 있습니다.  
  
 WCF와 함께 첫 번째 기술에는 Windows WF (Workflow Foundation) 했습니다. 워크플로 "활동"으로 캡슐화 하는 워크플로의 단계에서 응용 프로그램 개발을 단순화 Windows Workflow Foundation의 첫 번째 버전에서 개발자는 워크플로에 대 한 호스트를 만들어야 했습니다. 다음 버전의 Windows Workflow Foundation은 WCF와 통합 되었습니다. 워크플로 WCF 서비스에서 쉽게 호스팅할 수를 허용 합니다. 프로젝트 형식이 자동으로 WF/WCF를 선택 하 여이 작업을 수행 수에 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]합니다.  
  
 Microsoft BizTalk Server r 2 에서도 통신 기술로 WCF를 활용합니다. BizTalk는 표준화된 형식 간에 데이터를 전송 및 수신하도록 디자인되었습니다. 메시지는 중앙의 메시지 상자로 배달되어야 하며, 여기서 엄격한 매핑을 사용하거나 워크플로 엔진과 같은 BizTalk 기능 중 하나를 사용하여 메시지를 변환할 수 있습니다. 이제 BizTalk messagebox에 메시지를 전달할지 WCF 업무 (LOB) 어댑터를 사용할 수 있습니다.  
  
 Microsoft Silverlight는 상호 운용 가능하며 다양한 기능을 제공하는 웹 응용 프로그램을 만들기 위한 플랫폼입니다. 개발자는 이러한 웹 응용 프로그램을 통해 스트리밍 비디오 등의 다양한 미디어를 사용하는 웹 사이트를 만들 수 있습니다. 버전 2부터, Silverlight는 WCF Silverlight 응용 프로그램의 WCF 끝점을 연결 하는 통신 기술로 통합 되었습니다.  
  
 [!INCLUDE[dublin](../../../includes/dublin-md.md)] 응용 프로그램 서버 통신에 대 한 WCF를 사용 하는 응용 프로그램 관리 및 배포에 포함 됩니다. [!INCLUDE[dublin2](../../../includes/dublin2-md.md)] WCF 지원 응용 프로그램을 위해 특별히 설계 된 다양 한 도구 및 구성 옵션이 포함 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel>  
 [기본적인 Windows Communication Foundation 개념](../../../docs/framework/wcf/fundamental-concepts.md)  
 [Windows Communication Foundation 아키텍처](../../../docs/framework/wcf/architecture.md)  
 [지침 및 모범 사례](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [설명서에 대한 안내](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [기본 WCF 프로그래밍](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Windows Communication Foundation 샘플](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)
