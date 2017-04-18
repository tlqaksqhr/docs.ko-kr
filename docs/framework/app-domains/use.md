---
title: "응용 프로그램 도메인 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 도메인, 정보"
  - "공용 언어 런타임, 응용 프로그램 도메인"
  - "런타임, 응용 프로그램 도메인"
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 응용 프로그램 도메인 사용
응용 프로그램 도메인은 공용 언어 런타임에 사용되는 격리 단위를 제공합니다.  응용 프로그램 도메인은 프로세스 내에서 만들어지고 실행됩니다.  응용 프로그램 도메인은 대개 런타임 호스트에 의해 만들어집니다. 이 호스트의 역할은 런타임을 프로세스에 로드하고 응용 프로그램 도메인 내에서 사용자 코드를 실행하는 것입니다.  런타임 호스트에서는 프로세스와 기본 응용 프로그램 도메인을 만들고, 관리 코드를 런타임 호스트 내에서 실행합니다.  런타임 호스트에는 ASP.NET, Microsoft Internet Explorer 및 Windows 셸이 있습니다.  
  
 대부분의 응용 프로그램에서 사용자는 고유한 응용 프로그램 도메인을 만들 필요가 없습니다. 런타임 호스트에서 사용자를 대신해 필요한 모든 응용 프로그램 도메인을 만들어 줍니다.  그러나 응용 프로그램에서 코드를 격리하거나 DLL을 사용하고 언로드해야 하는 경우 추가 응용 프로그램 도메인을 만들고 구성할 수 있습니다.  
  
## 단원 내용  
 [방법: 응용 프로그램 도메인 만들기](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 응용 프로그램 도메인을 프로그래밍 방식으로 만드는 방법에 대해 설명합니다.  
  
 [방법: 응용 프로그램 도메인 언로드](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 응용 프로그램 도메인을 프로래밍 방식으로 언로드하는 방법에 대해 설명합니다.  
  
 [방법: 응용 프로그램 도메인 구성](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 응용 프로그램 도메인 구성 방법에 대해 설명합니다.  
  
 [응용 프로그램 도메인에서 설치 정보 검색](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 응용 프로그램 도메인에서 설치 정보를 검색하는 방법에 대해 설명합니다.  
  
 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 응용 프로그램 도메인에 어셈블리를 로드하는 방법에 대해 설명합니다.  
  
 [방법: 어셈블리에서 형식 및 멤버 정보 가져오기](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 어셈블리와 관련된 정보를 검색하는 방법에 대해 설명합니다.  
  
 [어셈블리 섀도 복사](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 어셈블리가 사용 중일 때 섀도 복사를 사용하여 어셈블리를 업데이트하는 방법과 섀도 복사를 구성하는 방법을 설명합니다.  
  
 [방법: 첫째 예외 알림 받기](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 예외가 되었음을 알려 주는 알림을 공용 언어 런타임에서 예외 처리기 검색을 시작하기 전에 받는 방법에 대해 설명합니다.  
  
 [어셈블리 로드 해결](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 어셈블리 로드 오류를 해결하기 위해 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 이벤트를 사용하는 방법에 대한 지침을 제공합니다.  
  
## 참조  
 <xref:System.AppDomain>  
 응용 프로그램 도메인을 나타냅니다.  응용 프로그램 도메인을 만들고 제어하기 위한 메서드를 제공합니다.  
  
## 관련 단원  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 어셈블리를 사용하여 실행하는 기능에 대해 설명합니다.  
  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 어셈블리의 특성을 만들고 서명하고 설정하는 방법에 대해 설명합니다.  
  
 [동적 메서드 및 어셈블리 생성](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 동적 어셈블리를 만드는 방법에 대해 설명합니다.  
  
 [응용 프로그램 도메인](../../../docs/framework/app-domains/application-domains.md)  
 응용 프로그램 도메인에 대해 개념적으로 설명합니다.  
  
 [리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)  
 **Reflection** 클래스를 사용하여 어셈블리와 관련된 정보를 얻는 방법에 대해 설명합니다.