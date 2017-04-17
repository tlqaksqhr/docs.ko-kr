---
title: "방법: Windows Communication Foundation 클라이언트 만들기 | Microsoft Docs"
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
  - "클라이언트 [WCF], 실행"
  - "WCF 클라이언트 [WCF], 실행"
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: 64
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 64
---
# 방법: Windows Communication Foundation 클라이언트 만들기
이 작업은 기본 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 필요한 6가지 작업 중 네 번째 작업입니다.6가지 작업의 개요를 모두 보려면 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목을 참조하십시오.  
  
 이 항목에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에서 메타데이터를 검색하고 이를 사용하여 서비스에 액세스할 수 있는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 프록시를 만드는 방법에 대해 설명합니다.이 작업은 Visual Studio에서 제공하는 서비스 참조 추가 기능을 사용하여 완료합니다.이 도구는 서비스의 MEX 끝점에서 메타데이터를 가져와 사용자가 선택한 언어를 사용하여 클라이언트 프록시에 대한 관리되는 소스 코드 파일을 생성합니다\(기본적으로 C\#\).클라이언트 프록시를 만드는 것 이외에 해당 도구는 클라이언트에 대한 구성 파일도 만들거나 업데이트합니다. 이 구성 파일을 사용하여 클라이언트 응용 프로그램에서 해당 끝점 중 하나의 서비스에 연결할 수 있습니다.  
  
> [!NOTE]
>  또한 Visual Studio 내의 서비스 참조 추가를 사용하는 대신 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구를 사용하여 프록시 클래스와 구성을 만들 수 있습니다.  
  
> [!WARNING]
>  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서 클래스 라이브러리 프로젝트의 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호출할 경우 서비스 참조 추가 기능을 사용하면 프록시 및 연결된 구성 파일을 자동으로 생성할 수 있습니다.이 구성 파일은 클래스 라이브러리 프로젝트에서는 사용되지 않습니다.생성된 구성 파일의 설정을 클래스 라이브러리를 호출하는 실행 파일의 app.config 파일에 추가해야 합니다.  
  
 클라이언트 응용 프로그램은 생성된 프록시 클래스를 사용하여 서비스와 통신합니다.이 절차에 대해서는 [방법: 클라이언트 사용](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)에서 설명합니다.  
  
### Windows Communication Foundation 클라이언트를 만들려면  
  
1.  Getting Started 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 프로젝트**를 차례로 선택하여 새 콘솔 응용 프로그램 프로젝트를 만듭니다.대화 상자의 왼쪽에 있는 **새 프로젝트 추가** 대화 상자에서 **C\#** 또는 **VB** 아래의 **Windows**를 선택합니다.대화 상자 가운데에서 **콘솔 응용 프로그램**을 선택합니다.프로젝트 이름을 `GettingStartedClient`로 지정합니다.  
  
2.  솔루션 탐색기에서 **GettingStartedClient**를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택하여 GettingStartedClient 프로젝트의 대상 프레임워크로 .NET Framework 4.5를 설정합니다.**대상 프레임워크** 드롭다운 목록에서 **.NET Framework 4.5**를 선택합니다.VB 프로젝트의 대상 프레임워크를 설정하는 방법은 약간 다릅니다. GettingStartedClient 프로젝트 속성 대화 상자에서 화면 왼쪽의 **컴파일** 탭을 클릭한 다음 대화 상자의 왼쪽 아래 모퉁이에 있는 **고급 컴파일 옵션** 단추를 클릭하십시오.그런 다음 **대상 프레임워크** 드롭다운 상자에서 **.NET Framework 4.5**를 선택합니다.  
  
     대상 프레임워크를 설정하면 Visual Studio 2011에서 솔루션을 다시 로드합니다. 메시지가 나타나면 **확인**을 누르십시오.  
  
3.  솔루션 탐색기에서 GettingStartedClient 프로젝트의 **References** 폴더를 마우스 오른쪽 단추로 클릭하여 System.ServiceModel에 대한 참조를 GettingStartedClient에 추가하고 **참조 추가**를 선택합니다.**참조 추가** 대화 상자에서 대화 상자 왼쪽의 **프레임워크**를 선택합니다.검색 어셈블리 텍스트 상자에 `System.ServiceModel`을 입력합니다.대화 상자 가운데에서 **System.ServiceModel**을 선택하고 **추가** 단추를 클릭한 다음 **닫기** 단추를 클릭합니다.주 메뉴에서 **모두 저장** 단추를 클릭하여 솔루션을 저장합니다.  
  
4.  그런 다음 계산기 서비스에 대한 서비스 참조를 추가합니다.그렇게 하기 전에 GettingStartedHost 콘솔 응용 프로그램을 실행해야 합니다.호스트가 실행되면 솔루션 탐색기의 GettingStartedClient 프로젝트에서 References 폴더를 마우스 오른쪽 단추로 클릭하고 서비스 참조 추가를 선택한 다음 서비스 참조 추가 대화 상자의 주소 상자에 URL\(http:\/\/localhost:8000\/ServiceModelSamples\/Service\)을 입력하고 **이동** 단추를 클릭합니다.서비스 목록 상자에 CalculatorService가 표시됩니다. CalculatorService를 두 번 클릭하면 확장되면서 서비스에서 구현한 서비스 계약이 표시됩니다.기본 네임스페이스를 그대로 두고 **확인** 단추를 클릭합니다.  
  
     Visual Studio를 사용하여 서비스에 대한 참조를 추가하면 솔루션 탐색기에서 GettingStartedClient 프로젝트 아래의 Service References 폴더에 새 항목이 나타납니다.[ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구를 사용하면 소스 코드 파일과 app.config 파일이 생성됩니다.  
  
     또한 적절한 스위치로 명령줄 도구 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 클라이언트 코드를 만들 수도 있습니다.다음 예제에서는 서비스에 대해 코드 파일 및 구성 파일을 생성합니다.첫 번째 예제는 VB에서 프록시를 생성하는 방법을 보여 주고 두 번째 예제는 C\#에서 프록시를 생성하는 방법을 보여 줍니다.  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
 클라이언트 응용 프로그램이 계산기 서비스를 호출하기 위해 사용할 프록시가 만들어졌습니다.일련의 항목 중 다음 항목을 계속 하십시오.[방법: 클라이언트 구성](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## 참고 항목  
 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [시작](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [자체 호스팅](../../../docs/framework/wcf/samples/self-host.md)   
 [방법: 구성 파일을 사용하여 서비스의 메타데이터 게시](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [방법: Svcutil.exe를 사용하여 메타데이터 문서 다운로드](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)