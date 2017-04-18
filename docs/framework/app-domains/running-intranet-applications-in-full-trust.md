---
title: "완전 신뢰 모드에서 인트라넷 응용 프로그램 실행 | Microsoft Docs"
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
  - "완전 신뢰, 인트라넷 응용 프로그램 실행"
  - "인트라넷 응용 프로그램, 완전 신뢰로 실행"
  - "완전 신뢰로 인트라넷 응용 프로그램 실행"
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# 완전 신뢰 모드에서 인트라넷 응용 프로그램 실행
.NET Framework 버전 3.5 SP1\(서비스 팩 1\)부터는 응용 프로그램과 해당 라이브러리 어셈블리를 네트워크 공유에서 완전 신뢰 어셈블리로 실행할 수 있습니다.  인트라넷 공유에서 로드한 어셈블리에는 <xref:System.Security.SecurityZone> 영역 증명 정보가 자동으로 추가됩니다.  이 증명 정보를 통해 컴퓨터에 있는 어셈블리와 동일한 권한 부여 집합\(일반적으로 완전 신뢰\)이 해당 어셈블리에 부여됩니다.  ClickOnce 응용 프로그램 또는 호스트에서 실행되도록 설계된 응용 프로그램에는 이 기능이 적용되지 않습니다.  
  
## 라이브러리 어셈블리에 대한 규칙  
 네트워크 공유에 있는 실행 파일에서 로드한 어셈블리에는 다음과 같은 규칙이 적용됩니다.  
  
-   라이브러리 어셈블리는 실행 가능 어셈블리와 같은 폴더에 있어야 합니다.  하위 폴더에 있거나 다른 경로에서 참조되는 어셈블리에는 완전 신뢰 권한 집합이 부여되지 않습니다.  
  
-   실행 파일에서 어셈블리를 지연 로드하는 경우 실행 파일을 시작하는 데 사용한 것과 같은 경로를 사용해야 합니다.  예를 들어, \\\\*network\-computer*\\*share* 라는 공유 위치를 드라이브 문자에 매핑한 경우 이 경로에서 실행 파일을 실행하면 실행 파일에서 네트워크 경로를 사용하여 로드한 어셈블리에 완전 신뢰가 부여되지 않습니다.  <xref:System.Security.SecurityZone> 영역에서 어셈블리를 지연 로드하려면 실행 파일에서 드라이브 문자 경로를 사용해야 합니다.  
  
## 이전 인트라넷 정책 복원  
 이전 버전의 .NET Framework에서는 공유된 어셈블리에 <xref:System.Security.SecurityZone> 영역 증명 정보가 부여되었습니다.  공유 위치에 있는 어셈블리에 완전 신뢰를 부여하려면 코드 액세스 보안 정책을 지정해야 했습니다.  
  
 이 새로운 동작은 인트라넷 어셈블리에 대한 기본 동작입니다.  이전 동작으로 돌아가려면 컴퓨터의 모든 응용 프로그램에 적용되는 레지스트리 키를 설정하여 <xref:System.Security.SecurityZone> 증명 정보를 제공합니다.  이 과정은 32비트 컴퓨터와 64비트 컴퓨터에서 서로 다릅니다.  
  
-   32비트 컴퓨터의 경우 시스템 레지스트리의 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 키 아래에 하위 키를 만듭니다.  키 이름은 LegacyMyComputerZone이고 사용할 값은 DWORD 값인 1입니다.  
  
-   64비트 컴퓨터의 경우 시스템 레지스트리의 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 키 아래에 하위 키를 만듭니다.  키 이름은 LegacyMyComputerZone이고 사용할 값은 DWORD 값인 1입니다.  HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework 키 아래에 동일한 하위 키를 만듭니다.  
  
## 참고 항목  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)