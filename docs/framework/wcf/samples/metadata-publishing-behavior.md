---
title: "메타데이터 게시 동작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fbccca0bb5db7fa12b5237d19b833e9fe11da0e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="metadata-publishing-behavior"></a>메타데이터 게시 동작
Metadata Publishing Behavior 샘플에서는 서비스의 메타데이터 게시 기능을 제어하는 방법을 보여 줍니다. 중요한 서비스 메타데이터를 실수로 공개하지 않도록 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스의 기본 구성에서는 메타데이터 게시를 사용하지 않도록 설정합니다. 이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.  
  
> [!IMPORTANT]
>  쉽게 구별할 수 있도록 이 샘플에서는 보안이 설정되지 않은 메타데이터 게시 끝점을 만드는 방법을 보여 줍니다. 이러한 끝점은 인증되지 않은 익명의 소비자가 사용할 수 있으므로 이러한 끝점을 배포하기 전에 서비스의 메타데이터를 공개하는 것이 적절한지 주의를 기울여야 합니다. 참조는 [메타 데이터 끝점을 보호 하는 사용자 지정](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) 메타 데이터 끝점을 보호 하는 샘플에 대 한 예제입니다.  
  
 샘플 기반는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 구현 하는 `ICalculator` 서비스 계약입니다. 이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 서비스에서 메타데이터를 노출하려면 서비스에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>가 구성되어야 합니다. 이 동작이 존재하는 경우 <xref:System.ServiceModel.Description.IMetadataExchange> 계약을 WS-MetadataExchange(MEX) 프로토콜의 구현으로 노출하도록 끝점을 구성함으로써 메타데이터를 게시할 수 있습니다. 편의상 이 계약에는 "IMetadataExchange"라는 약식 구성 이름이 지정되었습니다. 이 샘플에서는 보안 모드가 `mexHttpBinding`으로 설정된 `wsHttpBinding`과 동일한 `None`이라는 편리한 표준 바인딩을 사용합니다. "mex"의 상대 주소는 끝점에 사용되는데, 이를 서비스의 기본 주소와 비교하여 확인하는 경우 끝점 주소가 http://localhost/servicemodelsamples/service.svc/mex가 됩니다. 다음에서는 동작 구성을 보여 줍니다.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 다음에서는 MEX 끝점을 보여 줍니다.  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 이 샘플에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 속성을 `true`로 설정하며, 따라서 HTTP GET을 사용하여 서비스의 메타데이터를 노출합니다. HTTP GET 메타데이터 끝점을 사용하려면 서비스가 HTTP 기본 주소를 가져야 합니다. 서비스의 기본 주소에 쿼리 문자열 `?wsdl`을 사용하여 메타데이터에 액세스합니다. 예를 들어 웹 브라우저에서 서비스의 WSDL을 보려면 http://localhost/servicemodelsamples/service.svc?wsdl이라는 주소를 사용합니다. 또는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>를 `true`로 설정하여 HTTPS를 통해 메타데이터를 노출하는 데 이 동작을 사용할 수 있습니다. 이 경우 HTTPS 기본 주소가 필요합니다.  
  
 서비스의 MEX 끝점 사용 하 여 액세스 하는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 그러면 서비스의 메타데이터를 기준으로 클라이언트가 생성됩니다.  
  
 HTTP GET을 사용하여 서비스의 메타데이터에 액세스하려면 브라우저에서 http://localhost/servicemodelsamples/service.svc?wsdl로 이동합니다.  
  
 이 동작을 제거하고 서비스를 열려고 시도하면 예외가 발생합니다. 이 동작이 없으면 `IMetadataExchange` 계약이 구성된 끝점에 구현이 없으므로 그러한 오류가 발생합니다.  
  
 `HttpGetEnabled`를 `false`로 설정할 경우 서비스의 메타데이터 대신 CalculatorService 도움말 페이지가 나타납니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## <a name="see-also"></a>참고 항목
