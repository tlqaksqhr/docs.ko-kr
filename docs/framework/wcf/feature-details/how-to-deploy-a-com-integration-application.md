---
title: '방법: COM+ 통합 응용 프로그램 배포'
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: 872d0f0c84c1ac0ea96a87ed24a386bb9bedcf85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-deploy-a-com-integration-application"></a>방법: COM+ 통합 응용 프로그램 배포
COM+ 통합 응용 프로그램을 작성했다면 이를 다른 컴퓨터에 배포해야 하는 경우가 있습니다. 이 항목에서는 한 컴퓨터에서 다른 컴퓨터로 COM+ 통합 응용 프로그램을 이동하는 방법에 대해 설명합니다.  
  
### <a name="moving-a-com-hosted-integration-app"></a>COM+ 호스팅 통합 응용 프로그램 이동  
  
1.  두 컴퓨터 모두에서 WCF가 설치 되어 있는지 확인 합니다.  
  
2.  컴퓨터 A에서 응용 프로그램을 내보냅니다.  
  
3.  컴퓨터 B로 응용 프로그램을 가져옵니다.  
  
4.  응용 프로그램 루트 디렉터리를 설정합니다. 규칙에 따라 이는 %PROGRAMFILES%/ComPlus Applications/{AppGUID}입니다.  
  
5.  컴퓨터 A에 있는 응용 프로그램 루트 디렉터리의 Application.config 및 Application.manifest 파일을 컴퓨터 B의 응용 프로그램 루트 디렉터리로 복사합니다.  
  
6.  해당 컴퓨터를 식별하기 위해 컴퓨터 B의 Application.config 파일에서 서비스 끝점 주소를 편집합니다. 예를 들어 변경 http://machineA/MyService 를 http://machineB/MyService합니다.  
  
### <a name="moving-a-web-hosted-integration-application"></a>웹 호스팅 통합 응용 프로그램 이동  
  
1.  두 컴퓨터 모두에서 WCF가 설치 되어 있는지 확인 합니다.  
  
2.  컴퓨터 A에서 응용 프로그램을 내보냅니다.  
  
3.  컴퓨터 B로 응용 프로그램을 가져옵니다.  
  
4.  컴퓨터 B에서 IIS vroot를 만듭니다.  
  
5.  컴퓨터 A의 vroot에 있는 .svc 파일(componentName.svc) 및 Web.config 파일을 컴퓨터 B의 새로 만들어진 vroot로 복사합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM+ 응용 프로그램과 통합 개요](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [방법: COM+ 서비스 설정 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [방법: COM+ 서비스 모델 구성 도구 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
