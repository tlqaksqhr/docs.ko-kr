---
title: ".NET Framework 4.6 및 4.5 마이그레이션 가이드  | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, 응용 프로그램 마이그레이션"
  - "마이그레이션, .NET Framework "
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# .NET Framework 4.6 및 4.5 마이그레이션 가이드 
응용 프로그램이 이전 버전의 .NET Framework를 사용하여 만들어진 경우 일반적으로 .NET Framework 4.5 , 4.5.1 또는 4.6으로 쉽게 업그레이드할 수 있습니다. Visual Studio에서 프로젝트를 엽니다. 프로젝트가 이전 버전에서 만들어진 경우 **프로젝트 호환성** 대화 상자가 자동으로 열립니다. Visual Studio 2013의 프로젝트를 업그레이드하는 방법에 대한 자세한 내용은 [방법: Visual Studio의 이전 버전에서 만든 프로젝트 업그레이드](http://msdn.microsoft.com/library/vstudio/ms185327\(v=vs.100\).aspx) 및 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md)를 참조하세요.  
  
 그러나 .NET Framework에서 일부 사항을 변경하려면 코드를 변경해야 합니다. .NET Framework 4.5, 해당 포인트 릴리스 또는 .NET Framework 4.6의 새로운 기능을 활용할 수도 있습니다. 새 버전의 .NET Framework용 응용 프로그램으로 변경하는 이러한 유형의 작업을 일반적으로 *마이그레이션*이라고 합니다. 앱을 마이그레이션할 필요가 없는 경우 다시 컴파일하지 않고 .NET Framework 4.5 이상 버전에서 실행할 수 있습니다.  
  
## 마이그레이션 리소스  
 이전 버전의 .NET Framework에서 버전 4.5, 4.5.1 또는 4.5.2로 앱을 마이그레이션하기 전에는 다음 문서를 검토합니다.  
  
-   각 버전의 .NET Framework 내부에 있는 CLR 버전을 파악하고 앱을 대상으로 지정하기 위한 지침을 검토하려면 [버전 및 종속성](../../../docs/framework/migration-guide/versions-and-dependencies.md)을 참조하세요.  
  
-   앱에 영향을 줄 수 있는 런타임 및 대상 다시 지정 변경 내용과 이를 처리하기 위한 방법을 알아보려면 [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)을 검토하세요.  
  
-   코드에서 더 이상 사용되지 않는 형식 또는 멤버와 권장되는 대체 항목을 확인하려면 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)을 검토하세요.  
  
-   앱에 추가할 수 있는 새 기능에 대한 설명은 [새로운 기능](../../../docs/framework/whats-new/index.md)을 참조하세요.  
  
## 참고 항목  
 [4.5.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [4.5의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [.NET Framework 1.1에서 마이그레이션](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [버전 호환성](../../../docs/framework/migration-guide/version-compatibility.md)   
 [버전 및 종속성](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [방법: .NET Framework 4 또는 4.5를 지원하도록 응용 프로그램 구성](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [새로운 기능](../../../docs/framework/whats-new/index.md)   
 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)   
 [.NET Framework 버전 및 어셈블리 정보](http://go.microsoft.com/fwlink/?LinkId=201701)   
 [Microsoft .NET Framework 지원 기간 정책](http://go.microsoft.com/fwlink/?LinkId=196607)