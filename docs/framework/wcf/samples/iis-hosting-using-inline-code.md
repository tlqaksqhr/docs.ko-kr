---
title: "인라인 코드를 사용한 IIS 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "인라인 코드를 사용한 IIS 호스팅 샘플 [Windows Communication Foundation]"
  - "웹 호스팅 서비스"
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# 인라인 코드를 사용한 IIS 호스팅
이 샘플에서는 IIS\(인터넷 정보 서비스\)에서 호스팅하는 서비스를 구현하는 방법을 보여 줍니다. 여기서 서비스 코드는 .svc 파일에 인라인으로 포함되어 있으며 필요할 때 컴파일됩니다.또한 서비스 코드를 응용 프로그램의 \\App\_Code 디렉터리에 있는 소스 코드 파일에서 직접 구현하거나 \\bin에 배포된 어셈블리로 컴파일할 수 있습니다.이 샘플에서는 이러한 기술은 보여 주지 않습니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`  
  
 이 샘플에서는 요청\-회신 통신 패턴을 정의하는 계약을 구현하는 일반적인 서비스를 보여 줍니다.이 서비스는 IIS에서 호스팅되며 서비스 코드는 모두 Service.svc 파일에 포함되어 있습니다.서비스는 호스트에서 활성화되며 서비스로 전송된 첫 번째 메시지에 의해 필요할 때 컴파일됩니다.미리 컴파일할 필요는 없습니다.서비스는 다음 코드에 정의된 대로 `ICalculator` 계약을 구현합니다.  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 이 서비스 구현에서는 계산 후 해당 결과를 반환합니다.  
  
```  
<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>   
…  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  솔루션을 빌드한 후 setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다.이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.  
  
4.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.이 서비스를 호출할 수 있는 클라이언트 응용 프로그램을 만드는 방법을 보여 주는 예제는 [방법: 클라이언트 만들기](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)를 참조하십시오.  
  
## 참고 항목  
 [AppFabric 호스팅 및 지속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)