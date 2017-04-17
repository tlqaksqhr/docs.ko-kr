---
title: "문제 해결: 서비스 응용 프로그램이 설치되지 않을 경우 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서비스, 디버깅"
  - "서비스, 문제 해결"
  - "NT 서비스 문제 해결"
  - "서비스 응용 프로그램 문제 해결"
  - "Windows NT 서비스, 문제 해결"
  - "Windows 서비스 응용 프로그램, 문제 해결"
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# 문제 해결: 서비스 응용 프로그램이 설치되지 않을 경우
서비스 응용 프로그램이 제대로 설치되지 않을 경우 서비스 클래스의 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성 값을 해당 서비스의 설치 관리자에 있는 값과 동일하게 설정했는지 확인합니다.  서비스가 제대로 설치되려면 두 인스턴스에 있는 값이 동일해야 합니다.  
  
> [!NOTE]
>  설치 로그에서도 설치 프로세스에 대한 피드백을 얻을 수 있습니다.  
  
 또한 동일한 이름으로 설치된 다른 서비스가 있는지 확인해야 합니다.  설치에 성공하려면 서비스 이름이 고유해야 합니다.  
  
## 참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)