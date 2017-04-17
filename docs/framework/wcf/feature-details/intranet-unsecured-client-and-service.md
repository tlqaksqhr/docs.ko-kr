---
title: "보안이 설정되지 않은 인트라넷 클라이언트 및 서비스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: 20
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 20
---
# 보안이 설정되지 않은 인트라넷 클라이언트 및 서비스
다음 표에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 보안 사설망에 대한 정보를 제공하기 위해 개발된 간단한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 보여 줍니다.  데이터의 중요도가 낮거나, 네트워크가 원래 보안이 유지되거나, 보안이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라 아래 계층에서 제공되기 때문에 보안이 필요하지 않습니다.  
  
 ![보안이 설정되지 않은 인트라넷 클라이언트 및 서비스 시나리오](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")  
  
|특성|설명|  
|--------|--------|  
|보안 모드|없음|  
|전송|TCP|  
|바인딩|<xref:System.ServiceModel.NetTcpBinding>|  
|상호 운용성|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에만 해당|  
|인증|없음|  
|무결성|없음|  
|기밀성|없음|  
  
## 서비스  
 다음 코드와 구성은 독립적으로 실행되어야 합니다.  다음 작업 중 하나를 수행합니다.  
  
-   구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.  
  
-   제공된 구성을 사용하여 서비스를 만들지만 끝점을 정의하지 않습니다.  
  
### 코드  
 다음 코드는 보안 없이 끝점을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### 구성  
 다음 코드는 구성을 사용하여 동일한 끝점을 설정합니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## 클라이언트  
 다음 코드와 구성은 독립적으로 실행되어야 합니다.  다음 작업 중 하나를 수행합니다.  
  
-   이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.  
  
-   끝점 주소를 정의하지 않는 클라이언트를 만듭니다.  대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.  예를 들면 다음과 같습니다.  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### 코드  
 다음 코드는 TCP 프로토콜을 사용하여 보안이 설정되지 않은 끝점에 액세스하는 기본 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 보여 줍니다.  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### 구성  
 다음 구성 코드는 클라이언트에 적용됩니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.NetTcpBinding>   
 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Windows Server AppFabric에 대한 보안 모델](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)