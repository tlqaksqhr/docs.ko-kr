---
title: "방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용
[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]에서 웹 서비스를 호스트할 때 권한 부여 관리자를 응용 프로그램에 통합하여 서비스에 권한을 부여할 수 있습니다.  응용 프로그램 개발자는 권한 부여 관리자를 사용하여 개별 작업을 정의할 수 있습니다. 개별 작업은 그룹으로 분류되어 작업을 형성할 수 있습니다.  관리자는 역할에 특정 작업 또는 개별 작업을 수행할 권한을 부여할 수 있습니다.  권한 부여 관리자는 역할, 작업 및 사용자를 관리할 수 있도록 MMC\(Microsoft Management Console\) 스냅인과 같은 관리 도구를 제공합니다.  관리자는 XML 파일, Active Directory 또는 ADAM\(Active Directory Application Mode\) 저장소에서 권한 부여 관리자 정책 저장소를 구성합니다.  
  
 웹 서비스를 호스트하는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에 대한 권한 부여 관리자 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 구성하여 권한 부여 관리자를 응용 프로그램에 통합합니다.  다른 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자와 마찬가지로 권한 부여 관리자 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자도 \<`providers`\> 요소를 사용하여 구성됩니다.  
  
 다음 코드 예제는 권한 부여 관리자를 응용 프로그램에 통합하는 웹 서비스에 대한 구성 파일의 일부입니다.  
  
```  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 통합하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)를 참조하세요.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]에서 권한 부여 관리자를 사용하는 방법[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] [방법: ASP.NET 2.0에서 AzMan\(권한 부여 관리자\) 사용](http://go.microsoft.com/fwlink/?LinkId=71303)을 참조하세요.  
  
## 참고 항목  
 [방법: 서비스에서 ASP.NET 역할 공급자 사용](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)