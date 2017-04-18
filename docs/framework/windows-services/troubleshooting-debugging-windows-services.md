---
title: "문제 해결: Windows 서비스 디버깅 | Microsoft Docs"
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
  - "디버깅[Visual Studio], Windows 서비스"
  - "Windows 서비스 응용 프로그램 디버깅"
  - "서비스, 디버깅"
  - "서비스, 문제 해결"
  - "디버깅 문제 해결, Windows 서비스"
  - "서비스 응용 프로그램 문제 해결"
  - "Windows 서비스 응용 프로그램, 디버깅"
  - "Windows 서비스 응용 프로그램, 문제 해결"
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# 문제 해결: Windows 서비스 디버깅
Windows 서비스 응용 프로그램을 디버깅할 때 서비스와 **Windows 서비스 관리자**는 상호 작용합니다.  **서비스 관리자**는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 호출하여 서비스를 시작한 다음 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드가 반환될 때까지 30초를 기다립니다.  시간 안에 메서드가 반환되지 않으면 관리자는 서비스를 시작할 수 없다는 오류를 표시합니다.  
  
 [방법: Windows 서비스 응용 프로그램 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)에 설명된 대로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드를 디버깅할 때는 이 30초라는 시간에 유의해야 합니다.  <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드에 중단점을 설정한 경우 단계별 코드 실행이 30초 안에 이 메서드까지 도달하지 않으면 관리자에서 서비스를 시작하지 않습니다.  
  
## 참고 항목  
 [방법: Windows 서비스 응용 프로그램 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)