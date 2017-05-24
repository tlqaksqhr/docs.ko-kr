---
title: "방법: 메타데이터 검색 및 규격 서비스 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# 방법: 메타데이터 검색 및 규격 서비스 구현
서비스를 디자인하는 사람과 구현하는 사람이 다른 경우가 많습니다. 상호 운용하는 응용 프로그램이 중요한 환경에서는 WSDL(웹 서비스 기술 언어)로 계약을 디자인하거나 설명할 수 있으며 개발자는 제공된 계약에 따라 서비스를 구현해야 합니다. 기존 서비스를 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]로 마이그레이션하면서 통신 형식을 유지할 수도 있습니다. 또한 이중 계약에서는 호출자가 콜백 계약도 구현해야 합니다.  
  
 이러한 경우에 사용 해야는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (또는 이와 동등한 도구)를 서비스 계약 인터페이스 계약의 요구 사항을 충족 하기 위해 구현할 수 있는 관리 되는 언어로 생성 합니다. 일반적으로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 채널 팩터리와 함께 사용 되는 서비스 계약을 얻는 데 사용 됩니다 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 뿐만 아니라 올바른 바인딩 및 주소를 설정 하는 클라이언트 구성 파일에서와 마찬가지로 클라이언트 유형입니다. 생성된 구성 파일을 사용하려면 해당 파일을 서비스 구성 파일로 변경해야 합니다. 서비스 계약을 수정해야 할 수도 있습니다.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>데이터 검색 및 규격 서비스 구현  
  
1.  사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 메타 데이터 파일이 나 코드 파일을 생성 하는 메타 데이터 끝점에 대 한 합니다.  
  
2.  검색의 출력 코드 파일 (있는 경우 파일이 둘 이상)에서 필요한 인터페이스를 포함 하는로 표시 된 부분에는 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> 특성입니다. 다음 코드 예제에서 생성 된 두 개의 인터페이스를 보여 줍니다. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. 첫 번째(`ISampleService`)는 규격 서비스를 만들기 위해 구현하는 서비스 계약 인터페이스입니다. 두 번째 (`ISampleServiceChannel`) 도우미 인터페이스는 모두 서비스 계약 인터페이스를 확장 하는 및 <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> 및 클라이언트 응용 프로그램에서 사용 하기 위한 것입니다.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  WSDL에서 모든 작업에 대 한 회신 동작을 지정 하지 않으면 하는 경우 생성 되는 작업 계약 할 수는 <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> 속성이 와일드 카드 문자 (*)로 설정 합니다. 이 속성 설정을 제거합니다. 그렇지 않으면 서비스 계약 메타데이터를 구현할 때 해당 작업에 대해 메타데이터를 내보낼 수 없습니다.  
  
4.  클래스에서 인터페이스를 구현하고 서비스를 호스트합니다. 예를 들어 참조 [하는 방법: 서비스 계약 구현](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), 하거나 아래 예제 단원의 간단한 구현을 참조 하십시오.  
  
5.  클라이언트 구성에서 파일에 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 생성, 변경의 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) 구성 섹션을는 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 구성 섹션입니다. 생성되는 클라이언트 응용 프로그램 구성 파일의 예제를 보려면 다음 "예제" 단원을 참조하세요.  
  
6.  내에서 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 구성 섹션을 만듭니다는 `name` 특성에 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 서비스 구현 위한 구성 섹션입니다.  
  
7.  서비스 `name` 특성을 서비스 구현을 위한 구성 이름으로 설정합니다.  
  
8.  구현된 서비스 계약을 사용하는 끝점 구성 요소를 서비스 구성 섹션에 추가합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 실행 하 여 생성 된 코드 파일의 대부분을 보여 줍니다.는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 메타 데이터 파일에 대 한 합니다.  
  
 코드 내용은 다음과 같습니다.  
  
-   계약 요구 사항을 준수하는 서비스 계약 인터페이스(구현된 경우)(`ISampleService`).  
  
-   서비스 계약 인터페이스 모두를 확장 하는 도우미 인터페이스 및 <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> 및 클라이언트 응용 프로그램에 사용 하기 위한 (`ISampleServiceChannel`).  
  
-   확장 하는 도우미 클래스 <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> 및 클라이언트 응용 프로그램에 사용 하기 위한 (`SampleServiceClient`).  
  
-   서비스에서 생성된 구성 파일  
  
-   간단한 `ISampleService` 서비스 구현  
  
-   클라이언트측 구성 파일을 서비스측 버전으로 변환  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]  
  
 <!-- TODO: review snippet reference [!code[ClientProxyCodeSample#10](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/client.exe.config#10)]  -->
 <!-- TODO: review snippet reference [!code-csharp[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]  -->  
  
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]  
  
 <!-- TODO: review snippet reference [!code[ClientProxyCodeSample#20](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/hostapplication.exe.config#20)]  -->
 <!-- TODO: review snippet reference [!code-csharp[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]  -->  
  
## <a name="see-also"></a>참고 항목  
 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)