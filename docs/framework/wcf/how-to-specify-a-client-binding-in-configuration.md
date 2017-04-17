---
title: "방법: 구성에서 클라이언트 바인딩 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# 방법: 구성에서 클라이언트 바인딩 지정
이 예제에서는 계산기 서비스를 사용할 클라이언트 콘솔 응용 프로그램을 만들고 해당 클라이언트에 대한 바인딩을 구성에 선언적으로 지정합니다. 클라이언트 액세스는 `CalculatorService`를 구현 하는 `ICalculator` 인터페이스 및 서비스와 클라이언트 모두 사용 하 여는 <xref:System.ServiceModel.BasicHttpBinding> 클래스입니다.  
  
 설명된 프로시저에서는 계산기 서비스를 실행 중인 것으로 간주합니다. 서비스를 빌드하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 구성에서 서비스 바인딩 지정](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다. 또한 사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 자동으로 생성 된 클라이언트 구성 요소를 제공 합니다. 도구는 서비스 액세스를 위해 클라이언트 코드 및 구성을 생성합니다.  
  
 클라이언트는 두 가지 부분에 빌드됩니다. Svcutil.exe는 `ClientCalculator` 인터페이스를 구현하는 `ICalculator`를 생성합니다. 그런 다음 `ClientCalculator`의 인스턴스를 생성하여 이 클라이언트 응용 프로그램을 구성합니다.  
  
 일반적으로 바인딩 및 주소 정보를 코드에서 명령적으로 지정하지 않고 구성에서 선언적으로 지정하는 것이 좋습니다. 일반적으로 배포된 서비스의 바인딩과 주소가 서비스를 배포할 때 사용된 바인딩 및 주소와 다르기 때문에 코드로 끝점을 정의하는 것은 효과적이지 않습니다. 일반적으로 바인딩 및 주소 지정 정보를 코드와 구분하면 응용 프로그램을 다시 컴파일하거나 다시 배포할 필요 없이 해당 정보를 변경할 수 있습니다.  
  
 사용 하 여 다음 구성 단계를 모두 수행할 수는 [구성 편집기 도구 (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.  
  
 이 예제의 소스 복사에 대 한 참조는 [포함 한 기본 바인딩](../../../docs/framework/wcf/samples/basicbinding.md) 샘플입니다.  
  
### <a name="specifying-a-client-binding-in-configuration"></a>구성에서 클라이언트 바인딩 지정  
  
1.  명령줄에서 Svcutil.exe를 사용하여 서비스 메타데이터에서 코드를 생성합니다.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  생성된 클라이언트에는 클라이언트 구현에서 충족해야 하는 서비스 계약을 정의하는 `ICalculator` 인터페이스가 포함되어 있습니다.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3.  또한 생성된 클라이언트에는 `ClientCalculator`의 구현이 포함되어 있습니다.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4.  Svcutil.exe를 사용 하는 클라이언트에 대 한 구성을 생성은 <xref:System.ServiceModel.BasicHttpBinding> 클래스입니다. [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 사용하는 경우 이 파일 이름을 App.config로 지정합니다. 주소 및 바인딩 정보는 서비스 구현 내에 지정되지 않습니다. 또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.  
  
     [!code[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/common/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]  
  
5.  응용 프로그램에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6.  클라이언트를 컴파일하고 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [바인딩을 사용 하 여 서비스와 클라이언트를 구성 하려면](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)