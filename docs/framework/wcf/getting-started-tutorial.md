---
title: "초보자를 위한 자습서 | Microsoft Docs"
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
  - "시작 [WCF]"
  - "WCF [WCF], 시작"
  - "Windows Communication Foundation [WCF], 시작"
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# 초보자를 위한 자습서
이 단원에 포함된 항목에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 프로그래밍 기능에 대해 간략하게 설명합니다.  이 항목 아래쪽에 나열된 순서대로 진행하세요.  이 자습서를 수행하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 및 클라이언트 응용 프로그램을 만드는 데 필요한 단계에 대한 기초적인 이해를 할 수 있습니다.  서비스는 하나 이상의 끝점을 노출하며 각 끝점은 하나 이상의 서비스 작업을 노출합니다.  서비스의 *끝점*은 서비스를 찾을 수 있는 주소, 클라이언트가 서비스와 통신하는 방법을 설명하는 정보가 포함된 바인딩 및 서비스에서 클라이언트에 제공하는 기능을 정의하는 계약을 지정합니다.  
  
 이 자습서의 항목을 순서대로 수행하면 서비스를 실행하고 클라이언트에서 서비스를 호출할 수 있습니다.  첫 번째 세 개 항목에서는 서비스 계약을 정의하는 방법, 서비스 계약을 구현하는 방법 및 서비스를 호스트하는 방법을 설명합니다.  만들어진 서비스는 콘솔 응용 프로그램 내에서 자체 호스트됩니다.  IIS\(인터넷 정보 서비스\)에서 서비스를 호스트할 수도 있습니다.  이 작업을 수행하는 방법에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [방법: IIS에서의 WCF 서비스 호스팅](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)을 참조하세요.  서비스는 코드로 구성하지만 구성 파일 내에 서비스를 구성할 수도 있습니다.  구성 파일을 사용하는 방법에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [구성 파일을 사용하여 서비스 구성](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)을 참조하세요.  
  
 다음 세 개 항목에서는 클라이언트 프록시를 만드는 방법, 클라이언트 응용 프로그램을 구성하는 방법 및 클라이언트 프록시를 사용하여 서비스에서 노출하는 서비스 작업을 호출하는 방법을 설명합니다.  서비스는 클라이언트 응용 프로그램이 서비스와 통신하는 데 필요한 정보를 정의하는 메타데이터를 게시합니다.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서는 이 메타데이터에 액세스하는 프로세스를 자동화하고 해당 메타데이터를 사용하여 서비스에 대한 클라이언트 응용 프로그램을 생성 및 구성합니다.  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 사용하고 있지 않은 경우에는 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스에 대한 클라이언트 응용 프로그램을 생성 및 구성할 수 있습니다.  
  
 이 단원에 있는 모든 항목에서는 Visual Studio 2011을 개발 환경으로 사용하는 것으로 간주합니다.  다른 개발 환경을 사용하는 경우에는 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] 관련 지침을 무시하세요.  
  
> [!NOTE]
>  [!INCLUDE[wv](../../../includes/wv-md.md)] 또는 그 이상 버전의 Windows 운영 체제를 실행 중인 경우에는 시작 메뉴로 이동한 다음 Visual Studio 2011을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택하여 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]를 시작해야 합니다.  Visual Studio 2011을 항상 관리자 권한으로 시작하려면 바로 가기를 만들어 마우스 오른쪽 단추로 클릭한 다음 속성을 선택하세요. 여기서 **호환성** 탭을 선택하고 **관리자 권한으로 이 프로그램 실행** 확인란을 선택하세요.  이 바로 가기로 Visual Studio 2011을 시작하면 프로그램이 항상 관리자 권한으로 실행됩니다.  
  
 하드 디스크에 다운로드하여 실행할 수 있는 샘플 응용 프로그램은 [Windows Communication Foundation Samples](http://msdn.microsoft.com/ko-kr/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)을 참조하세요.  특히 이 항목에 대해서는 [시작](../../../docs/framework/wcf/samples/getting-started-sample.md)을 참조하세요.  
  
 서비스 및 클라이언트 만들기에 대한 자세한 내용은 [기본 WCF 프로그래밍](../../../docs/framework/wcf/basic-wcf-programming.md)을 참조하세요.  
  
## 단원 내용  
 [방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 사용자 정의 인터페이스를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 계약을 만드는 방법을 설명합니다.  계약은 서비스에서 노출하는 기능을 정의합니다.  
  
 [방법: 서비스 계약 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 서비스 계약을 구현하는 방법에 대해 설명합니다.  정의된 계약은 서비스 클래스를 사용하여 구현해야 합니다.  
  
 [방법: 기본 서비스 호스트 및 실행](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 코드에서 서비스의 끝점을 구성하는 방법 및 콘솔 응용 프로그램에서 서비스를 호스트하는 방법을 설명합니다.  서비스를 활성화하려면 런타임 환경에 구성하고 호스트해야 합니다.  이 환경에서 서비스를 만들고 서비스의 컨텍스트 및 수명을 제어합니다.  
  
 [방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 프록시를 만드는 데 사용되는 메타데이터를 검색하는 방법을 설명합니다.  이 프로세스는 Visual Studio 2011의 서비스 참조 추가 기능을 사용합니다.  
  
 [방법: 클라이언트 구성](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 WCF 클라이언트를 구성하는 방법을 설명합니다. 클라이언트를 구성하려면 클라이언트에서 서비스에 액세스하는 데 사용하는 끝점을 지정해야 합니다.  
  
 [방법: 클라이언트 사용](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 프록시를 사용하여 서비스 작업을 호출하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## 관련 단원  
 [Windows Communication Foundation Samples](http://msdn.microsoft.com/ko-kr/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [기본 프로그래밍 수명 주기](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## 참고 항목  
 [개념적 개요](../../../docs/framework/wcf/conceptual-overview.md)   
 [설명서에 대한 안내](../../../docs/framework/wcf/guide-to-the-documentation.md)   
 [Windows Communication Foundation 정의](../../../docs/framework/wcf/whats-wcf.md)   
 [WCF 기능 정보](../../../docs/framework/wcf/feature-details/index.md)