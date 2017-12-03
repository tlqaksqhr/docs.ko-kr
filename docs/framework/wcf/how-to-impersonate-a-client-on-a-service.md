---
title: "방법: 서비스에서 클라이언트 가장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de7bfb7d926f9aa75ccfcfe8a550a0dbae4e12ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-impersonate-a-client-on-a-service"></a><span data-ttu-id="d63a9-102">방법: 서비스에서 클라이언트 가장</span><span class="sxs-lookup"><span data-stu-id="d63a9-102">How to: Impersonate a Client on a Service</span></span>
<span data-ttu-id="d63a9-103">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스에서 클라이언트 가장을 사용하면 서비스가 클라이언트를 대신하여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-103">Impersonating a client on a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service enables the service to perform actions on behalf of the client.</span></span> <span data-ttu-id="d63a9-104">예를 들어, 시스템의 디렉터리 및 파일에 대한 액세스 또는 SQL Server 데이터베이스에 대한 액세스와 같이 ACL(액세스 제어 목록) 검사 관련 작업의 경우 ACL 검사는 클라이언트 사용자 계정에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-104">For actions subject to access control list (ACL) checks, such as access to directories and files on a machine or access to a SQL Server database, the ACL check is against the client user account.</span></span> <span data-ttu-id="d63a9-105">이 항목에서는 Windows 도메인의 클라이언트를 사용하여 클라이언트 가장 수준을 설정하는 데 필요한 기본적인 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-105">This topic shows the basic steps required to enable a client in a Windows domain to set a client impersonation level.</span></span> <span data-ttu-id="d63a9-106">이와 관련된 작업 예제는 [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d63a9-106">For a working example of this, see [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="d63a9-107">클라이언트 가장 참조 [위임 및 가장](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-107"> client impersonation, see [Delegation and Impersonation](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d63a9-108">클라이언트 및 서비스가 동일한 컴퓨터에서 실행 중이고 클라이언트가 시스템 계정( `Local System` 또는 `Network Service`)으로 실행 중인 경우, 상태 저장 보안 컨텍스트 토큰을 사용하여 보안 세션을 설정할 때 클라이언트를 가장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-108">When the client and service are running on the same computer and the client is running under a system account (that is, `Local System` or `Network Service`), the client cannot be impersonated when a secure session is established with stateful Security Context tokens.</span></span> <span data-ttu-id="d63a9-109">일반적으로 WinForms 또는 콘솔 응용 프로그램은 현재 계정에 로그인된 상태에서 실행되기 때문에 기본적으로 계정을 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-109">A WinForms or console application typically is run under the currently logged in account, so that account can be impersonated by default.</span></span> <span data-ttu-id="d63a9-110">그러나 클라이언트가 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지이고 해당 페이지가 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 또는 IIS 7.0에서 호스팅된 경우 클라이언트는 기본적으로 `Network Service` 계정으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-110">However, when the client is an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page and that page is hosted in [!INCLUDE[iis601](../../../includes/iis601-md.md)] or IIS 7.0, then the client does run under the `Network Service` account by default.</span></span> <span data-ttu-id="d63a9-111">보안 세션을 지원하는 모든 시스템 제공 바인딩은 기본적으로 상태 비저장 보안 컨텍스트 토큰을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-111">All of the system-provided bindings that support secure sessions use a stateless Security Context token by default.</span></span> <span data-ttu-id="d63a9-112">그러나 클라이언트가 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지이고 상태 저장 보안 컨텍스트 토큰을 통한 보안 세션을 사용하는 경우, 클라이언트를 가장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-112">However, if the client is an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page and secure sessions with stateful Security Context tokens are used, the client cannot be impersonated.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="d63a9-113">상태 저장 보안 컨텍스트 토큰을 사용 하 여 보안 세션에서 참조 [하는 방법: 보안 세션에 대 한 보안 컨텍스트 토큰 만들기](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-113"> using stateful Security Context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a><span data-ttu-id="d63a9-114">서비스에서 캐시된 Windows 토큰에서 클라이언트 가장을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="d63a9-114">To enable impersonation of a client from a cached Windows token on a service</span></span>  
  
1.  <span data-ttu-id="d63a9-115">서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-115">Create the service.</span></span> <span data-ttu-id="d63a9-116">이 기본 프로시저에 대한 자습서는 [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d63a9-116">For a tutorial of this basic procedure, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="d63a9-117"><xref:System.ServiceModel.NetTcpBinding> 또는 <xref:System.ServiceModel.WSHttpBinding>과 같이 Windows 인증을 사용하여 세션을 만드는 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-117">Use a binding that uses Windows authentication and creates a session, such as <xref:System.ServiceModel.NetTcpBinding> or <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
3.  <span data-ttu-id="d63a9-118">서비스 인터페이스의 가장을 만드는 경우 <xref:System.ServiceModel.OperationBehaviorAttribute> 클래스를 클라이언트 가장이 필요한 메서드에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-118">When creating the implementation of the service's interface, apply the <xref:System.ServiceModel.OperationBehaviorAttribute> class to the method that requires client impersonation.</span></span> <span data-ttu-id="d63a9-119"><xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> 속성을 <xref:System.ServiceModel.ImpersonationOption.Required>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-119">Set the <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> property to <xref:System.ServiceModel.ImpersonationOption.Required>.</span></span>  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a><span data-ttu-id="d63a9-120">클라이언트에서 허용된 가장 수준으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d63a9-120">To set the allowed impersonation level on the client</span></span>  
  
1.  <span data-ttu-id="d63a9-121">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 클라이언트 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-121">Create service client code by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="d63a9-122">[WCF 클라이언트를 사용 하 여 서비스에 액세스](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-122"> [Accessing Services Using a WCF Client](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="d63a9-123">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만든 후 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 클래스의 <xref:System.ServiceModel.Security.WindowsClientCredential> 속성을 <xref:System.Security.Principal.TokenImpersonationLevel> 열거형 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-123">After creating the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, set the <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property of the <xref:System.ServiceModel.Security.WindowsClientCredential> class to one of the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration values.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d63a9-124"><xref:System.Security.Principal.TokenImpersonationLevel.Delegation>을 사용하려면 협상된 Kerberos 인증( *multi-leg* 또는 *multi-step* Kerberos라고도 함)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-124">To use <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, negotiated Kerberos authentication (sometimes called *multi-leg* or *multi-step* Kerberos) must be used.</span></span> <span data-ttu-id="d63a9-125">이 구현 하는 방법에 대 한 참조 [보안에 대 한 유용한](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a9-125">For a description of how to implement this, see [Best Practices for Security](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).</span></span>  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d63a9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d63a9-126">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 [<span data-ttu-id="d63a9-127">클라이언트 가장</span><span class="sxs-lookup"><span data-stu-id="d63a9-127">Impersonating the Client</span></span>](../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 [<span data-ttu-id="d63a9-128">위임 및 가장</span><span class="sxs-lookup"><span data-stu-id="d63a9-128">Delegation and Impersonation</span></span>](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
