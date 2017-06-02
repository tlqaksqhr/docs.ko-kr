---
title: "방법: 관리되는 응용 프로그램에서 WCF 서비스 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# 방법: 관리되는 응용 프로그램에서 WCF 서비스 호스팅
관리되는 응용 프로그램 내에서 서비스를 호스팅하려면 관리되는 응용 프로그램 코드 내에 서비스에 대한 코드를 포함하고, 코드에서 명령적으로, 구성을 통해 선언적으로 또는 기본 끝점을 사용해 서비스에 대한 끝점을 정의한 다음 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.  
  
 메시지 받기를 시작하려면 <xref:System.ServiceModel.ServiceHost>에서 <xref:System.ServiceModel.ICommunicationObject.Open%2A>을 호출합니다.이렇게 하면 서비스에 대한 수신기가 만들어지고 열립니다.관리되는 응용 프로그램이 호스팅 작업을 직접 수행하므로 이런 방식으로 서비스를 호스팅하는 것을 "자체 호스팅"이라고 합니다.서비스를 닫으려면 <xref:System.ServiceModel.ServiceHost>에서 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=fullName>를 호출합니다.  
  
 서비스는 관리되는 Windows 서비스, IIS\(인터넷 정보 서비스\) 또는 WAS\(Windows Process Activation Service\)에서 호스팅될 수도 있습니다.서비스 호스팅 옵션에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [서비스 호스팅](../../../docs/framework/wcf/hosting-services.md)을 참조하십시오.  
  
 관리되는 응용 프로그램에서 서비스를 호스팅할 경우 최소한의 배포 인프라를 필요로 하기 때문에 가장 유연한 옵션입니다.관리되는 응용 프로그램에서 서비스 호스팅에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [관리되는 응용 프로그램에서의 호스팅](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)을 참조하십시오.  
  
 다음 절차에서는 콘솔 응용 프로그램에서 자체 호스팅된 서비스를 구현하는 방법을 보여 줍니다.  
  
### 자체 호스팅된 서비스를 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 열고 **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트…**를 선택합니다.  
  
2.  **설치된 템플릿** 목록에서 **Visual C\#**, **Windows** 또는 **Visual Basic**, **Windows**를 선택합니다.[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 설정에 따라 이들 옵션 중 하나 또는 둘 모두 **설치된 템플릿** 목록의 **다른 언어** 노드 아래에 있을 수 있습니다.  
  
3.  **Windows** 목록에서 **콘솔 응용 프로그램**을 선택합니다.**이름** 상자에 `SelfHost`를 입력하고 **확인**을 클릭합니다.  
  
4.  **솔루션 탐색기**에서 **SelfHost**를 마우스 오른쪽 단추로 클릭하고 **참조 추가…**를 선택합니다.**.NET** 탭에서 **System.ServiceModel**을 선택하고 **확인**을 클릭합니다.  
  
    > [!TIP]
    >  **솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기**를 선택합니다.  
  
5.  **Program.cs** 또는 **Module1.vb**가 아직 열려 있지 않으면 **솔루션 탐색기**에서 두 번 클릭하여 코드 창에서 엽니다.파일 맨 위에 다음 문을 추가합니다.  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  서비스 계약을 정의 및 구현합니다.이 예제에서는 서비스에 대한 입력을 기준으로 메시지를 반환하는 `HelloWorldService`를 정의합니다.  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  서비스 인터페이스를 정의 및 구현하는 방법[!INCLUDE[crabout](../../../includes/crabout-md.md)][방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) 및 [방법: 서비스 계약 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)을 참조하십시오.  
  
7.  서비스의 기본 주소를 사용하여 `Main` 메서드 맨 위에 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들어 서비스 형식 및 기본 주소 URI\(Uniform Resource Identifier\)를 나타내는 <xref:System.Type>을 [ServiceHost\(Type, Uri\<xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>에 전달합니다.메타데이터 게시를 사용하도록 설정한 다음 <xref:System.ServiceModel.ServiceHost>에서 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 메서드를 호출하여 서비스를 초기화하고 메시지를 받도록 서비스를 준비합니다.  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     <!-- TODO: review snippet reference [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]  -->  
  
    > [!NOTE]
    >  이 예제에서는 기본 끝점을 사용하며, 이 서비스에는 구성 파일이 필요하지 않습니다.끝점을 구성하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 끝점을 하나씩 만듭니다.기본 끝점[!INCLUDE[crabout](../../../includes/crabout-md.md)][단순화된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하십시오.  
  
9. Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
### 서비스를 테스트하려면  
  
1.  서비스를 실행하려면 Ctrl\+F5를 누릅니다.  
  
2.  **WCF 테스트 클라이언트**를 엽니다.  
  
    > [!TIP]
    >  **WCF 테스트 클라이언트**를 열려면 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 **WcfTestClient.exe**를 실행합니다.  
  
3.  **파일** 메뉴에서 **서비스 추가...**를 선택합니다.  
  
4.  주소 상자에 `http://localhost:8080/hello`를 입력하고 **확인**을 클릭합니다.  
  
    > [!TIP]
    >  서비스가 실행 중인지 확인하십시오. 그렇지 않으면 이 단계는 실패합니다.코드에서 기본 주소를 변경한 경우에는 이 단계에서 수정된 기본 주소를 사용하십시오.  
  
5.  **내 서비스 프로젝트** 노드 아래의 **SayHello**를 두 번 클릭하고**요청** 목록의 **값** 열에 사용자 이름을 입력한 다음 **호출**을 클릭합니다.그러면 **응답** 목록에 회신 메시지가 나타납니다.  
  
## 예제  
 다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 개체를 만들어 `HelloWorldService` 형식의 서비스를 호스팅한 다음 <xref:System.ServiceModel.ServiceHost>에서 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 메서드를 호출합니다.기본 주소는 코드에서 제공되고 메타데이터 게시가 사용하도록 설정되며 기본 끝점이 사용됩니다.  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## 참고 항목  
 <xref:System.Uri>   
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>   
 <xref:System.Configuration.ConfigurationManager>   
 [방법: IIS에서의 WCF 서비스 호스팅](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)   
 [자체 호스팅](../../../docs/framework/wcf/samples/self-host.md)   
 [서비스 호스팅](../../../docs/framework/wcf/hosting-services.md)   
 [방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)   
 [방법: 서비스 계약 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)   
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)