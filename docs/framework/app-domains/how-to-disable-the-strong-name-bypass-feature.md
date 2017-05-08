---
title: "방법: 강력한 이름 건너뛰기 기능 비활성화 | Microsoft Docs"
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
  - "강력한 이름 건너뛰기 기능"
  - "강력한 이름의 어셈블리, 신뢰할 수 있는 응용 프로그램 도메인으로 로드"
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: 30
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 30
---
# 방법: 강력한 이름 건너뛰기 기능 비활성화
.NET Framework 버전 3.5 서비스 팩 1\(SP1\)부터는 어셈블리가 완전 신뢰 <xref:System.AppDomain> 개체\(예: `MyComputer` 영역의 기본 <xref:System.AppDomain>\)에 로드될 때 강력한 이름 서명의 유효성이 검사되지 않습니다.  이를 강력한 이름 건너뛰기 기능이라고 합니다.  완전 신뢰 환경에서는 서명된 완전 신뢰 어셈블리에 대한 <xref:System.Security.Permissions.StrongNameIdentityPermission> 요청이 해당 서명에 관계없이 항상 성공합니다.  유일한 제한 사항은 해당 영역이 완전 신뢰되므로 어셈블리가 완전 신뢰되어야 한다는 것입니다.  이러한 조건에서 강력한 이름은 결정적인 요소가 아니므로 유효성을 검사할 필요가 없습니다.  강력한 이름 서명의 유효성 검사를 건너뛰면 성능이 크게 향상됩니다.  
  
 건너뛰기 기능은 서명이 연기되지 않았으며 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성에 지정된 디렉터리에서 완전 신뢰 <xref:System.AppDomain>에 로드된 모든 완전 신뢰 어셈블리에 적용됩니다.  
  
 레지스트리 키 값을 설정하여 컴퓨터의 모든 응용 프로그램에 대한 건너뛰기 기능을 재정의할 수 있습니다.  단일 응용 프로그램에 대한 설정을 재정의하려면 응용 프로그램 구성 파일을 사용합니다.  레지스트리 키에 의해 건너뛰기 기능이 비활성화된 경우 단일 응용 프로그램에서 건너뛰기 기능을 다시 사용할 수는 없습니다.  
  
 건너뛰기 기능을 재정의하면 강력한 이름이 올바른지만 검사되고 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 검사되지 않습니다.  특정 강력한 이름을 확인하려면 해당 검사를 별도로 수행해야 합니다.  
  
> [!IMPORTANT]
>  강력한 이름 유효성 검사를 적용할 수 있는지 여부는 다음 절차에 설명된 대로 레지스트리 키에 의해 결정됩니다.  응용 프로그램이 해당 레지스트리 키에 액세스하는 데 필요한 ACL\(액세스 제어 목록\) 권한이 없는 계정을 사용하여 실행되는 경우 설정이 적용되지 않습니다.  ACL 권한은 모든 어셈블리에 대해 읽을 수 있도록 이 키에 대해 구성되어야 합니다.  
  
### 모든 응용 프로그램에 대한 강력한 이름 건너뛰기 기능을 비활성화하려면  
  
-   32비트 컴퓨터의 경우 시스템 레지스트리의 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 키 아래에 값이 0인 `AllowStrongNameBypass`라는 이름의 DWORD 항목을 만듭니다.  
  
-   64비트 컴퓨터의 경우 시스템 레지스트리의 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 및 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework 키 아래에 값이 0인 `AllowStrongNameBypass`라는 이름의 DWORD 항목을 만듭니다.  
  
### 단일 응용 프로그램에 대한 강력한 이름 건너뛰기 기능을 비활성화하려면  
  
1.  응용 프로그램 구성 파일을 열거나 만듭니다.  
  
     이 파일에 대한 자세한 내용은 [응용 프로그램 구성](../../../docs/framework/configure-apps/index.md)의 응용 프로그램 구성 파일 단원을 참조하십시오.  
  
2.  다음 항목을 추가합니다.  
  
    ```  
    <configuration>  
      <runtime>  
         < bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 구성 파일 설정을 제거하거나 특성을 "true"로 설정하면 응용 프로그램에 대한 건너뛰기 기능을 복원할 수 있습니다.  
  
> [!NOTE]
>  컴퓨터에서 건너뛰기 기능이 설정된 경우에만 응용 프로그램에 대한 강력한 이름 유효성 검사를 설정하거나 해제할 수 있습니다.  컴퓨터에서 건너뛰기 기능이 해제되어 있으면 모든 응용 프로그램에서 강력한 이름의 유효성이 검사되며 단일 응용 프로그램에서 유효성 검사를 건너뛸 수 없습니다.  
  
## 참고 항목  
 [Sn.exe\(강력한 이름 도구\)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [\<bypassTrustedAppStrongNames\> 요소](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)   
 [강력한 이름의 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)