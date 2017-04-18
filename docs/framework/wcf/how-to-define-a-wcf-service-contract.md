---
title: "방법: Windows Communication Foundation 서비스 계약 정의 | Microsoft Docs"
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
helpviewer_keywords: 
  - "서비스 계약 [WCF], 정의"
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: 58
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 58
---
# 방법: Windows Communication Foundation 서비스 계약 정의
이 작업은 기본 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 필요한 6가지 작업 중 첫 번째 작업입니다.6가지 작업의 개요를 모두 보려면 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목을 참조하십시오.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 만들 때 첫 번째 작업은 계약을 정의하는 것입니다.서비스 계약은 서비스가 지원하는 작업을 지정합니다.작업은 웹 서비스 메서드로 간주될 수 있습니다.C\+\+, C\# 또는 VB\(Visual Basic\) 인터페이스를 정의하여 계약을 만듭니다.인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다.각 인터페이스에는 <xref:System.ServiceModel.ServiceContractAttribute>가 적용되어야 하고 각 작업에는 <xref:System.ServiceModel.OperationContractAttribute> 특성이 적용되어야 합니다.<xref:System.ServiceModel.ServiceContractAttribute> 특성을 포함하는 인터페이스 내에 있는 메서드에 <xref:System.ServiceModel.OperationContractAttribute> 특성이 없으면 서비스에 의해 해당 메서드가 노출되지 않습니다.  
  
 이 작업에 사용되는 코드는 이 절차 다음에 나오는 예제에 제공되어 있습니다.  
  
### 서비스 계약을 정의하려면  
  
1.  **시작** 메뉴에서 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]를 마우스 오른쪽 단추로 클릭한 다음 **관리자 권한으로 실행**을 선택하여 해당 프로그램을 관리자로 엽니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭하여 WCF 서비스 라이브러리 프로젝트를 만듭니다.**새 프로젝트** 대화 상자의 왼쪽에서 C\# 프로젝트의 **Visual C\#** 또는 **다른 언어**를 확장한 다음 Visual Basic 프로젝트의 **Visual Basic**을 확장합니다.선택된 언어에서 **WCF**를 선택하면 대화 상자 가운데에 프로젝트 템플릿 목록이 표시됩니다.**WCF** 서비스 라이브러리를 선택하고 **이름** 텍스트 상자에 `GettingStartedLib`를 입력하고 대화 상자 아래쪽의 **솔루션 이름** 텍스트 상자에 `GettingStarted`를 입력합니다.  
  
3.  Visual Studio에서 세 파일 IService1.cs\(또는 IService1.vb\), Service1.cs\(또는 Service1.vb\) 및 App.config가 포함된 프로젝트를 만듭니다.IService1 파일에는 기본 서비스 계약이 포함되어 있습니다.Service1 파일에는 서비스 계약의 기본 구현이 포함되어 있습니다.App.config 파일에는 Visual Studio WCF 서비스 호스트가 포함된 기본 서비스를 로드하는 데 필요한 구성이 포함되어 있습니다.WCF 서비스 호스트 도구에 대한 자세한 내용은 [WCF 서비스 호스트\(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)를 참조하십시오.  
  
4.  IService1.cs 또는 IService1.vb 파일을 열고 네임스페이스 선언 안의 코드를 삭제하고 네임스페이스 선언은 그대로 둡니다.다음 코드와 같이 네임스페이스 선언 내에 `ICalculator`라는 새 인터페이스를 정의합니다.  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
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
    }  
  
    ```  
  
    ```  
    ‘IService.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
        Public Interface ICalculator  
  
            <OperationContract()> _  
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
        End Interface  
    End Namespace  
  
    ```  
  
     이 계약은 온라인 계약을 정의합니다.`ICalculator` 인터페이스에는 <xref:System.ServiceModel.ServiceContractAttribute> 특성이 표시되어 있습니다.이 특성은 계약 이름을 명확히 나타내는 데 사용하는 네임스페이스를 정의합니다.각 계산기 연산에는 <xref:System.ServiceModel.OperationContractAttribute> 특성이 표시되어 있습니다.  
  
    > [!NOTE]
    >  특성을 사용하여 인터페이스, 멤버 또는 클래스에 주석을 달 때 특성 이름에서 "특성" 부분을 삭제할 수 있습니다.따라서 <xref:System.ServiceModel.ServiceContractAttribute>는 `[ServiceContract]`\(C\#의 경우\) 또는 `<ServiceContract>`\(Visual Basic의 경우\)가 됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>   
 [방법: 서비스 계약 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)   
 [시작](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [자체 호스팅](../../../docs/framework/wcf/samples/self-host.md)