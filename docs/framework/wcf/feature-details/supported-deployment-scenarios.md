---
title: 지원되는 배포 시나리오
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: d0afd12b1c17f9356146aa13c90f8db65ed9ec0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="supported-deployment-scenarios"></a>지원되는 배포 시나리오
부분 신뢰 응용 프로그램에서 사용 하기 위해 지원 되는 Windows Communication Foundation (WCF) 기능 하위 집합은 WCF를 사용 하는 작업의 일부는 아니지만 일부를 시나리오의 요구 사항을 충족 하도록 설계 되었습니다. 서버에서 WCF 인터넷 규모의 요구 사항을 만족 공유로 타사 응용 프로그램을 실행 하는 호스팅 공급자에는 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 보통 신뢰 권한 집합 보안상의 이유로 합니다. 클라이언트에서 WCF 부분 신뢰 지원이 디자인에 같은 배포 기술의 요구 사항을 충족 하도록 [ClickOnce 배포](http://go.microsoft.com/fwlink/?LinkId=83712) 또는 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]의 원활 하 고 보안을 허용 하는 XAML 브라우저 응용 프로그램 기술 신뢰할 수 없는 사이트에서 데스크톱 응용 프로그램 배포입니다.  
  
## <a name="minimum-permission-requirements"></a>최소 권한 요구 사항  
 WCF는 다음과 같은 표준 명명 된 권한 집합 중 하나에서 실행 중인 응용 프로그램의 기능 하위 집합을 지원 합니다.  
  
-   보통 신뢰 권한  
  
-   인터넷 영역 권한  
  
 더 제한적인 권한으로 부분 신뢰 응용 프로그램에서 WCF를 사용 하려고 런타임에 보안 예외가 발생할 수 있습니다.  
  
 이러한 권한 집합에서 지원되는 기능에 대한 자세한 내용은 [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)을 참조하십시오.  
  
## <a name="partial-trust-on-the-server"></a>서버 측의 부분 신뢰  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램 호스팅 서비스의 상용 공급자는 대부분 해당 서버에서 실행하는 응용 프로그램을 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 보통 신뢰 권한 집합에서 실행해야 합니다. WCF 서비스 이러한 환경에서 실행할 수 있습니다를 사용 하는 <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, 또는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 전송 수준 보안으로 합니다.  
  
 보통 신뢰 호스팅 환경에서 실행 되는 WCF 서비스를 다른 서버에 클라이언트 요청에 대 한 응답 메시지를 보내서 중간 계층 서비스와도 작동할 수 있습니다. 서버에서 중간 계층 시나리오는 호스팅 환경이 응용 프로그램에 적합한 <xref:System.Net.WebPermission> 을 부여해서 원하는 서버로 아웃바운드 요청을 한 경우 지원됩니다.  
  
 지원 되는 SOAP 바인딩 중 하나를 사용 하 여 SOAP 메시징 외에도 WCF 지원는 <xref:System.ServiceModel.WebHttpBinding> 부분적으로 신뢰할 수 있는 응용 프로그램에서 웹 스타일 서비스를 구축 하기 위한 합니다. [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [WCF 배포](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), 및 [AJAX 통합 및 JSON 지원](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) WCF의 기능을 모두 부분 신뢰에서 지원 됩니다.  
  
 워크플로 서비스는 완전 신뢰 권한이 필요하며, 부분 신뢰 응용 프로그램에서 사용할 수 없습니다.  
  
 자세한 내용은 참조 [하는 방법: ASP.NET 2.0에서 사용 하 여 보통 신뢰](http://go.microsoft.com/fwlink/?LinkId=84603)합니다.  
  
## <a name="partial-trust-on-the-client"></a>클라이언트 측의 부분 신뢰  
 신뢰할 수 없는 인터넷 사이트에서 코드를 다운로드하고 실행할 때 특정 보안 조치를 취해야 합니다. [ClickOnce 배포](http://go.microsoft.com/fwlink/?LinkId=83712) 및 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]의 XBAP(XAML 브라우저 응용 프로그램) 기술은 둘 다 부분 신뢰를 사용하여 제한된 권한(인터넷 영역)을 신뢰할 수 없는 코드에 부여합니다.  
  
 WCF에서 배포한 부분 신뢰 응용 프로그램 내에서 원격 서버와 통신 하는 데 사용 수 [ClickOnce 배포](http://go.microsoft.com/fwlink/?LinkId=83712) 또는 XBAP 합니다. 인터넷 영역 권한 집합에 포함 되어 <xref:System.Net.WebPermission> 이러한 응용 프로그램에 설명 된 지원 되는 WCF 바인딩 중 하나를 사용 하 여 원래 서버와 통신을 허용 하는 원래 호스트에 대 한 [부분 신뢰 기능 호환성 ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>참고 항목  
 [코드 액세스 보안](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [Windows Presentation Foundation 브라우저에서 호스팅되는 응용 프로그램 개요](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [부분 신뢰](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [ASP.Net 보통 신뢰](http://go.microsoft.com/fwlink/?LinkId=69328)
