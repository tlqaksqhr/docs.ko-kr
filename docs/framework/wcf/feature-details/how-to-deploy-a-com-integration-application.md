---
title: "방법: COM+ 통합 응용 프로그램 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 방법: COM+ 통합 응용 프로그램 배포
COM\+ 통합 응용 프로그램을 작성했다면 이를 다른 컴퓨터에 배포해야 하는 경우가 있습니다.이 항목에서는 한 컴퓨터에서 다른 컴퓨터로 COM\+ 통합 응용 프로그램을 이동하는 방법에 대해 설명합니다.  
  
### COM\+ 호스팅 통합 응용 프로그램 이동  
  
1.  두 컴퓨터 모두에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 설치되어 있는지 확인합니다.  
  
2.  컴퓨터 A에서 응용 프로그램을 내보냅니다.  
  
3.  컴퓨터 B로 응용 프로그램을 가져옵니다.  
  
4.  응용 프로그램 루트 디렉터리를 설정합니다.규칙에 따라 이는 %PROGRAMFILES%\/ComPlus Applications\/{AppGUID}입니다.  
  
5.  컴퓨터 A에 있는 응용 프로그램 루트 디렉터리의 Application.config 및 Application.manifest 파일을 컴퓨터 B의 응용 프로그램 루트 디렉터리로 복사합니다.  
  
6.  해당 컴퓨터를 식별하기 위해 컴퓨터 B의 Application.config 파일에서 서비스 끝점 주소를 편집합니다.예를 들어 http:\/\/machineA\/MyService를 http:\/\/machineB\/MyService로 변경합니다.  
  
### 웹 호스팅 통합 응용 프로그램 이동  
  
1.  두 컴퓨터 모두에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 설치되어 있는지 확인합니다.  
  
2.  컴퓨터 A에서 응용 프로그램을 내보냅니다.  
  
3.  컴퓨터 B로 응용 프로그램을 가져옵니다.  
  
4.  컴퓨터 B에서 IIS vroot를 만듭니다.  
  
5.  컴퓨터 A의 vroot에 있는 .svc 파일\(componentName.svc\) 및 Web.config 파일을 컴퓨터 B의 새로 만들어진 vroot로 복사합니다.  
  
## 참고 항목  
 [COM\+ 응용 프로그램과 통합 개요](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)   
 [방법: COM\+ 서비스 설정 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)   
 [방법: COM\+ 서비스 모델 구성 도구 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)