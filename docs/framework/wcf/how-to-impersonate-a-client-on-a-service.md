---
title: "방법: 서비스에서 클라이언트 가장 | Microsoft Docs"
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
  - "WCF, 가장"
  - "가장"
  - "WCF, 보안"
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: 33
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 33
---
# 방법: 서비스에서 클라이언트 가장
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스에서 클라이언트 가장을 사용하면 서비스가 클라이언트를 대신하여 작업을 수행할 수 있습니다. 예를 들어, 시스템의 디렉터리 및 파일에 대한 액세스 또는 SQL Server 데이터베이스에 대한 액세스와 같이 ACL\(액세스 제어 목록\) 검사 관련 작업의 경우 ACL 검사는 클라이언트 사용자 계정에 대해 수행됩니다. 이 항목에서는 Windows 도메인의 클라이언트를 사용하여 클라이언트 가장 수준을 설정하는 데 필요한 기본적인 단계에 대해 설명합니다. 이와 관련된 작업 예제는 [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)을 참조하십시오. 클라이언트 가장에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [위임 및 가장](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)을 참조하십시오.  
  
> [!NOTE]
>  클라이언트 및 서비스가 동일한 컴퓨터에서 실행 중이고 클라이언트가 시스템 계정\(`Local System` 또는 `Network Service`\)으로 실행 중인 경우, 상태 저장 보안 컨텍스트 토큰을 사용하여 보안 세션을 설정할 때 클라이언트를 가장할 수 없습니다. 일반적으로 WinForms 또는 콘솔 응용 프로그램은 현재 계정에 로그인된 상태에서 실행되기 때문에 기본적으로 계정을 가장할 수 있습니다. 그러나 클라이언트가 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지이고 해당 페이지가 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 또는 IIS 7.0에서 호스팅된 경우 클라이언트는 기본적으로 `Network Service` 계정으로 실행됩니다. 보안 세션을 지원하는 모든 시스템 제공 바인딩은 기본적으로 상태 비저장 보안 컨텍스트 토큰을 사용합니다. 그러나 클라이언트가 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지이고 상태 저장 보안 컨텍스트 토큰을 통한 보안 세션을 사용하는 경우, 클라이언트를 가장할 수 없습니다. 보안 세션에서 상태 저장 보안 컨텍스트 토큰을 사용하는 방법에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)을 참조하십시오.  
  
### 서비스에서 캐시된 Windows 토큰에서 클라이언트 가장을 사용하려면  
  
1.  서비스를 만듭니다. 이 기본 프로시저에 대한 자습서는 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)를 참조하십시오.  
  
2.  <xref:System.ServiceModel.NetTcpBinding> 또는 <xref:System.ServiceModel.WSHttpBinding>과 같이 Windows 인증을 사용하여 세션을 만드는 바인딩을 사용합니다.  
  
3.  서비스 인터페이스의 가장을 만드는 경우 <xref:System.ServiceModel.OperationBehaviorAttribute> 클래스를 클라이언트 가장이 필요한 메서드에 적용합니다.<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> 속성을 <xref:System.ServiceModel.ImpersonationOption>으로 설정합니다.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### 클라이언트에서 허용된 가장 수준으로 설정하려면  
  
1.  [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 클라이언트 코드를 만듭니다.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [WCF 클라이언트를 사용하여 서비스 액세스](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만든 후 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 클래스의 <xref:System.ServiceModel.Security.WindowsClientCredential> 속성을 <xref:System.Security.Principal.TokenImpersonationLevel> 열거형 값 중 하나로 설정합니다.  
  
    > [!NOTE]
    >  <xref:System.Security.Principal.TokenImpersonationLevel>을 사용하려면 협상된 Kerberos 인증\(*multi\-leg* 또는 *multi\-step* Kerberos라고도 함\)을 사용해야 합니다. 이 작업을 구현하는 방법에 대한 자세한 내용은 [보안을 위한 최선의 방법](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)을 참조하십시오.  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## 참고 항목  
 <xref:System.ServiceModel.OperationBehaviorAttribute>   
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)   
 [위임 및 가장](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)