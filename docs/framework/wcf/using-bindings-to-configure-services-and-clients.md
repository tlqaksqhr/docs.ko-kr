---
title: 바인딩을 사용하여 서비스 및 클라이언트 구성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings [WCF], using
ms.assetid: c39479c3-0766-4a17-ba4c-97a74607f392
caps.latest.revision: 33
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 68c8c2c93ce29147247c332848025fd931bf7854
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="using-bindings-to-configure-services-and-clients"></a>바인딩을 사용하여 서비스 및 클라이언트 구성
바인딩은 끝점에 연결하는 데 필요한 통신 세부 사항을 지정하는 개체입니다. 보다 구체적으로, 바인딩에는 해당 끝점이나 클라이언트 채널에 사용할 전송, 통신 형식(메시지 인코딩) 및 프로토콜의 고유 정보를 정의하여 클라이언트 또는 서비스 런타임을 만드는 데 사용되는 구성 정보가 들어 있습니다. 작동하는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스를 만들려면 서비스의 각 끝점에 바인딩이 필요합니다. 이 항목에서는 바인딩 정의, 바인딩이 정의되는 방법 및 끝점에 대해 특정 바인딩이 지정되는 방법에 대해 설명합니다.  
  
## <a name="what-a-binding-defines"></a>바인딩이 정의하는 내용  
 바인딩의 정보는 매우 기본적이거나 매우 복잡할 수 있습니다. 가장 기본적인 바인딩은 끝점에 연결하는 데 사용해야 하는 HTTP 등의 전송 프로토콜만 지정합니다. 보다 일반적으로, 끝점 연결 방법과 관련해서 바인딩에 포함되는 정보는 다음 표의 범주 중 하나에 해당합니다.  
  
 프로토콜  
 신뢰할 수 있는 메시징 기능 또는 트랜잭션 컨텍스트 흐름 설정 중 하나인 사용되는 보안 메커니즘을 결정합니다.  
  
 전송  
 사용할 내부 전송 프로토콜(예: TCP 또는 HTTP)을 결정합니다.  
  
 Encoding  
 텍스트/XML, 이진 또는 MTOM(Message Transmission Optimization Mechanism) 등 메시지가 통신 중 바이트 스트림으로 표현되는 방법을 결정하는 메시지 인코딩을 결정합니다.  
  
## <a name="system-provided-bindings"></a>시스템 제공 바인딩  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에는 대부분의 응용 프로그램 요구 사항과 시나리오를 다루는 시스템 제공 바인딩 집합이 포함됩니다. 다음 클래스는 시스템 제공 바인딩의 몇 가지 예를 나타냅니다.  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: ASP.NET 웹 서비스[ASMX] 기반 서비스 등 웹 서비스에 연결하는 데 적합한, WS-I Basic Profile 1.1 사양을 준수하는 HTTP 프로토콜 바인딩입니다.  
  
-   <xref:System.ServiceModel.WSHttpBinding>: 끝점에 연결하는 데 적합한, 웹 서비스 사양 프로토콜을 준수하는 HTTP 프로토콜 바인딩입니다.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: Windows 명명된 파이프 전송과 함께 .NET 이진 인코딩 및 프레이밍 기술을 사용하여 동일한 컴퓨터의 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 끝점에 연결합니다.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: MSMQ라고도 하는 메시지 큐와 함께 .NET 이진 인코딩 및 프레이밍 기술을 사용하여 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 끝점과의 대기 중인 메시지 연결을 만듭니다.  
  
 설명 된 시스템 제공 바인딩에의 전체 목록을 참조 하십시오. [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)합니다.  
  
## <a name="custom-bindings"></a>사용자 지정 바인딩  
 시스템 제공 바인딩 컬렉션에 서비스 응용 프로그램에서 필요로 하는 기능의 올바른 조합이 포함되지 않은 경우 <xref:System.ServiceModel.Channels.CustomBinding> 바인딩을 만들 수 있습니다. 요소에 대 한 자세한 내용은 <xref:System.ServiceModel.Channels.CustomBinding> 참조 바인딩 [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 및 [사용자 지정 바인딩](../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
## <a name="using-bindings"></a>바인딩 사용  
 바인딩 사용은 다음 두 가지 기본 단계로 이루어집니다.  
  
1.  바인딩을 선택하거나 정의합니다. 가장 쉬운 방법은 시스템 제공 바인딩 중 하나를 선택하고 기본 설정을 사용하는 것입니다. 시스템 제공 바인딩을 선택하고 요구 사항에 맞게 속성 값을 다시 설정할 수도 있습니다. 또는 사용자 지정 바인딩을 만들고 필요에 따라 모든 속성을 설정할 수 있습니다.  
  
2.  이 바인딩을 사용하는 끝점을 만듭니다.  
  
## <a name="code-and-configuration"></a>코드 및 구성  
 코드 또는 구성을 통해 바인딩을 정의하거나 구성할 수 있습니다. 이러한 두 방법은 사용되는 바인딩 형식에 관계가 없습니다. 예를 들어 시스템 제공 바인딩 또는 <xref:System.ServiceModel.Channels.CustomBinding> 바인딩을 사용하는지에 관계가 없습니다. 일반적으로 코드를 사용하면 컴파일 시 바인딩 정의를 완전히 제어할 수 있습니다. 반면 구성을 사용하는 경우 시스템 관리자나 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 또는 클라이언트의 사용자가 바인딩의 매개 변수를 변경할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램이 배포될 특정 컴퓨터 요구 사항과 네트워크 상태를 예측할 방법이 없으므로 이 유연성은 바람직한 경우가 많습니다. 바인딩(및 주소 지정) 정보를 코드와 구분하면 관리자가 응용 프로그램을 다시 컴파일하거나 다시 배포할 필요 없이 바인딩 세부 정보를 변경할 수 있습니다. 바인딩이 코드에서 정의된 경우 구성 파일에서 수행된 구성 기반 정의를 재정의합니다. 이러한 방법의 예는 다음 항목을 참조하세요.  
  
-   [방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md) 코드에서 바인딩을 만드는의 예제를 제공 합니다.  
  
-   [방법: 클라이언트 구성](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md) 구성을 사용 하 여 클라이언트를 만드는 예제를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [방법: 구성에서 서비스 바인딩 지정](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [방법: 코드에서 서비스 바인딩 지정](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)  
 [방법: 구성에서 클라이언트 바인딩 지정](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)  
 [방법: 코드에서 클라이언트 바인딩 지정](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-code.md)
