---
title: ".NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기 | Microsoft Docs"
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
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework, 시스템 다시 시작 감소"
  - "설치 [.NET Framework]"
  - ".NET Framework 설치"
ms.assetid: 7aa8cb72-dee9-4716-ac54-b17b9ae8218f
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# .NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로그램은 설치과정 중에 시스템이 다시 시작하는것을 방지하기 위해 [다시 시작 관리자](http://go.microsoft.com/fwlink/?LinkId=231425) 를 사용합니다.  응용 프로그램 설치 프로그램에서 .NET Framework를 설치하는 경우 이 기능을 이용하도록 다시 시작 관리자와 인터페이스할 수 있습니다.  자세한 내용은 [방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)을 참조하십시오.  
  
## 다시 시작 하는 이유  
 .NET Framework 4 응용 프로그램이 설치 동안 사용 중인 경우 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 위해서는 시스템을 다시 시작해야 합니다.  이는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 .NET Framework 4 파일을 대체하고 이러한 파일을 설치하는 동안 제공되어야 하기 때문입니다.  대부분의 경우 사용 중인 .NET Framework 4 응용 프로그램을 먼저 감지하고 닫아 다시 시작되는 것을 방지할 수 있습니다.  그러나, 일부 시스템 응용 프로그램은 닫지 말아야 합니다.  이 경우 다시 시작해야 합니다.  
  
## 최종 사용자 환경  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 전체 설치를 수행하고 있는 최종 사용자에게는 설치 프로그램에서 .NET Framework 4 응용 프로그램을 사용 중인 것을 감지한 경우 시스템을 다시 시작하는 것을 방지할 기회가 제공됩니다.  메시지는 실행 중인 모든 .NET Framework 4 응용 프로그램을 나열하며 설치하기 전에 이러한 응용 프로그램을 닫는 옵션을 제공합니다.  사용자가 확인하는 경우 이러한 응용 프로그램은 설치 프로그램에 의해 종료되고 시스템이 다시 시작되지 않습니다.  사용자가 특정 시간 내에 메시지에 응답하지 않는 경우 응용 프로그램을 닫지 않고 설치가 계속됩니다.  
  
 실행 중인 응용 프로그램이 닫힌 경우에도 다시 시작 관리자가 시스템을 다시 시작해야 하는 상황을 감지하는 경우 메시지는 표시되지 않습니다.  
  
 ![응용 프로그램 닫기 대화 상자](../../../docs/framework/deployment/media/closeapplicationdialog.png "CloseApplicationDialog")  
사용 중인 .NET Framework 응용 프로그램을 닫기 확인  
  
## 연결된 설치 관리자 사용  
 응용 프로그램과 함께 .NET Framework를 재배포하되 자체 설치 프로그램과 UI를 사용하고 싶은 경우 해당 설치 프로세스에 .NET Framework 설치 프로세스를 포함\(연결\)할 수 있습니다.  연결된 설치에 대한 자세한 내용은 [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)를 참조하십시오.  연결된 설치에서 시스템이 다시 시작되는 사례를 줄이려면 .NET Framework 설치 관리자는 닫을 응용 프로그램 목록이 포함된 설치 프로그램을 제공합니다.  설치 프로그램은 메시지 상자와 같은 사용자 인터페이스를 통해 사용자에게 이 정보를 제공하고 사용자의 응답을 가져온 후 .NET Framework 설치 관리자에게 응답을 다시 전달해야 합니다.  연결된 설치 프로그램의 예는 문서 [방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)를 참조하십시오.  
  
 연결된 설치 프로그램을 사용하고 있지만 응용 프로그램을 닫는 자체 메시지 상자를 제공하고 싶지 않은 경우 .NET Framework 설치 프로세스를 연결할 때 명령줄에서 `/showrmui` 및 `/passive` 옵션을 사용할 수 있습니다.  이러한 옵션을 함께 사용하면 설치 관리자가 시스템이 다시 시작되지 않도록 응용 프로그램을 닫을 수 있다면 응용 프로그램을 닫으라는 메시지 상자를 표시합니다.  이 메시지 상자는 전체 사용자 인터페이스에서와 같이 passive 모드에서 동일하게 작동합니다.  .NET Framework 재배포 가능 패키지의 명령줄 옵션의 전체 집합은 [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)를 참조하십시오.  
  
## 참고 항목  
 [배포](../../../docs/framework/deployment/net-framework-and-applications.md)   
 [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)   
 [방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)