---
title: "서비스 설명 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# 서비스 설명
Service Description 샘플에서는 런타임에 서비스에서 서비스 설명 정보를 검색하는 방법을 보여 줍니다.이 샘플은 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)을 기반으로 하며 서비스에 대한 설명 정보를 반환하도록 추가 서비스 작업이 정의되었습니다.반환되는 정보는 서비스의 기본 주소 및 끝점을 나열합니다.서비스는 <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> 및 <xref:System.ServiceModel.Description.ServiceDescription> 클래스를 사용하여 이 정보를 제공합니다.  
  
 이 샘플에서 클라이언트는 콘솔 응용 프로그램\(.exe\)이고 서비스는 IIS\(인터넷 정보 서비스\)를 통해 호스팅됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에는 `IServiceDescriptionCalculator`라는 계산기 계약의 수정된 버전이 있습니다.이 계약에서는 서비스의 기본 주소 및 서비스 끝점을 설명하는 여러 줄의 문자열을 클라이언트에 반환하는 `GetServiceDescriptionInfo`라는 추가 서비스 작업을 정의합니다.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
  
```  
  
 `GetServiceDescriptionInfo`의 구현 코드에서는 <xref:System.ServiceModel.Description.ServiceDescription>을 사용하여 서비스 끝점을 나열합니다.서비스 끝점은 상대 주소를 가질 수 있으므로 먼저 서비스의 기본 주소를 나열합니다.이 정보를 모두 가져오기 위해 코드는 <xref:System.ServiceModel.OperationContext.Current%2A>를 사용하여 작업 컨텍스트를 가져옵니다.<xref:System.ServiceModel.ServiceHost> 및 해당 <xref:System.ServiceModel.Description.ServiceDescription> 개체는 작업 컨텍스트로부터 검색됩니다.서비스의 기본 끝점을 나열하기 위해 코드는 서비스 호스트의 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> 컬렉션에서 반복합니다.서비스의 서비스 끝점을 나열하기 위해 코드는 서비스 설명의 끝점 컬렉션에서 반복합니다.  
  
```  
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
  
```  
  
 샘플을 실행하면 계산기 작업 및 `GetServiceDescriptionInfo` 작업에서 반환되는 서비스 정보가 나타납니다.클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
  
## 참고 항목