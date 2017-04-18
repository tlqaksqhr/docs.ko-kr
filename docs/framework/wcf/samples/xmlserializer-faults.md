---
title: "XMLSerializer 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# XMLSerializer 오류
<xref:System.Xml.Serialization.XmlSerializer>Fault Contract 샘플은 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 오류 정보를 서비스에서 클라이언트로 전달하는 방법을 보여 줍니다.  이 샘플은 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)에 기반을 두고 있으며 내부 예외를 오류로 변환하기 위해 일부 코드가 서비스에 추가되었습니다.  클라이언트는 서비스에서 오류 조건을 강제하기 위해 0으로 나누기를 시도합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 다음 샘플 코드와 같이 계산기 계약은 <xref:System.ServiceModel.FaultContractAttribute>를 포함하도록 수정되었습니다.  또한 <xref:System.Xml.Serialization.XmlSerializer>를 사용한 serialization을 지원하도록 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 사용합니다.  이 특성에 대해 <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> 속성이 `true`로 설정되어 오류를 읽고 쓰는 데 <xref:System.Xml.Serialization.XmlSerializer>를 사용하도록 serializer에 지시합니다.  
  
```  
[XmlSerializerFormat(SupportFaults=true)]  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
  
    [OperationContract]  
    int Subtract(int n1, int n2);  
  
    [OperationContract]  
    int Multiply(int n1, int n2);  
  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 클라이언트 프록시용 코드를 생성할 때는 **\/UseSerializerForFaults** 플래그를 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)에 적용해야 합니다.  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## 참고 항목  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>   
 <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>