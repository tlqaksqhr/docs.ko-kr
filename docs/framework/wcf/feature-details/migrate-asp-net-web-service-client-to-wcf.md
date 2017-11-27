---
title: "방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0a22a7-e1d5-4718-8997-4319a7cd9027
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d77e07cca938b67f5b79416ac4d8fdef96739ed2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-client-code-to-the-windows-communication-foundation"></a>방법: ASP.NET 웹 서비스 클라이언트 코드를 Windows Communication Foundation으로 마이그레이션
다음 절차에서는 ASP.NET 웹 서비스 클라이언트 코드를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션하기 위해 수행해야 하는 전체 단계에 대해 설명합니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-migrate-aspnet-web-service-client-code-to-wcf"></a>ASP.NET 웹 서비스 클라이언트 코드를 WCF로 마이그레이션하려면  
  
1.  클라이언트에 대한 종합적인 테스트 집합이 존재하는지 확인합니다.  
  
2.  Visual Studio 2005를 사용하여 클라이언트 응용 프로그램을 .NET 2.0으로 업그레이드합니다. 테스트 집합을 실행합니다.  
  
3.  클라이언트 프로젝트에서 ASP.NET 클라이언트 코드를 제거합니다. 해당 코드는 WSDL.exe 도구를 사용하여 생성된 모듈에 있습니다.  
  
4.  생성 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 사용 하 여 클라이언트 코드는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. 해당 코드를 클라이언트 프로젝트에 추가하고, 구성 출력을 클라이언트의 기존 구성 파일로 병합합니다.  
  
5.  응용 프로그램을 컴파일합니다. 이전 ASP.NET 클라이언트 형식에 대한 참조를 새 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 형식에 대한 참조로 교체하여 컴파일 오류를 복구합니다.  
  
6.  테스트 집합을 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Communication Foundation에 ASP.NET 웹 서비스 코드 마이그레이션](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)
