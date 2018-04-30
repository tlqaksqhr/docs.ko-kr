---
title: '방법: ASP.NET 멤버 자격 공급자 사용'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19fb83d21c77f3206c314a2e6c40562fcb75f151
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="34525-102">방법: ASP.NET 멤버 자격 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="34525-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="34525-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 개발자가 웹 사이트를 만들어 사용자에게 고유 사용자 이름 및 암호 조합을 만들 수 있도록 해주는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="34525-104">이 기능을 사용하여 사용자는 사이트에 계정을 설정하고 사이트 및 해당 서비스에 로그인하여 단독으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34525-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="34525-105">반면, Windows 보안의 경우 사용자에게는 Windows 도메인의 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="34525-106">대신 자신의 자격 증명(사용자 이름/암호 조합)을 제공하는 사용자가 사이트 및 해당 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34525-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="34525-107">샘플 응용 프로그램에 대 한 참조 [멤버 자격 및 역할 공급자](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="34525-108">사용 하는 방법에 대 한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자 기능 참조 [하는 방법: ASP.NET 역할 공급자를 사용 하 여 서비스와](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-108">For information about using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="34525-109">멤버 자격 기능을 사용하려면 SQL Server 데이터베이스를 사용하여 사용자 정보를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="34525-110">해당 기능에는 암호를 잊은 사용자에게 질문을 표시하기 위한 메서드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="34525-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="34525-111"> 개발자는 보안을 위해 이러한 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34525-111"> developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="34525-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 통합된 경우 사용자는 사용자 이름/암호 조합을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램에 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-112">When integrated into an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="34525-113">데이터를 전송 하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 같은 사용자 이름/암호 자격 증명을 지 원하는 바인딩을 사용는 <xref:System.ServiceModel.WSHttpBinding> (구성에서는 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) 하 고 클라이언트 자격 증명 설정 입력 `UserName`합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-113">To transfer the data to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="34525-114">서비스에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안이 사용자 이름 및 암호를 기반으로 사용자를 인증하고, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할에서 지정한 역할도 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-114">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security authenticates the user based on the user name and password, and also assigns the role specified by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="34525-115">에서는 사용자 이름/암호 조합 또는 기타 사용자 정보로 데이터베이스를 입력할 수 있는 메서드를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34525-115"> does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="34525-116">멤버 자격 공급자를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="34525-116">To configure the membership provider</span></span>  
  
1.  <span data-ttu-id="34525-117">Web.config 파일에 아래에서 <`system.web`> 요소를 만들는 <`membership`> 요소.</span><span class="sxs-lookup"><span data-stu-id="34525-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2.  <span data-ttu-id="34525-118">`<membership>` 요소 아래에 `<providers>` 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34525-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3.  <span data-ttu-id="34525-119">하위 항목으로 <`providers`> 요소를 추가 `<clear />` 요소 플러시 공급자의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4.  <span data-ttu-id="34525-120">아래는 `<clear />` 요소를 만들기는 <`add`> 요소는 다음 특성으로 적절 한 값으로 설정: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` `requiresUniqueEmail`, 및 `passwordFormat`합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="34525-121">`name` 특성은 나중에 구성 파일의 값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34525-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="34525-122">다음 예제에서는 이 특성을 `SqlMembershipProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="34525-123">다음 예제에서는 구성 섹션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34525-123">The following example shows the configuration section.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="34525-124">사용자 이름/암호 조합을 허용하도록 서비스 보안을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="34525-124">To configure service security to accept the user name/password combination</span></span>  
  
1.  <span data-ttu-id="34525-125">구성 파일에 아래에서 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 추가 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2.  <span data-ttu-id="34525-126">추가 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 바인딩 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34525-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="34525-127">만들기에 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 참조 바인딩 요소 [하는 방법: 구성에서 서비스 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-127">For more information about creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3.  <span data-ttu-id="34525-128">`mode` 요소의 `<security>` 특성을 `Message`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4.  <span data-ttu-id="34525-129">설정의 `clientCredentialType` 특성에는 <`message`> 요소를 `UserName`합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="34525-130">이를 통해 사용자 이름/암호 쌍을 클라이언트의 자격 증명으로 사용하도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="34525-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="34525-131">다음 예제에서는 바인딩에 대한 구성 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34525-131">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="34525-132">멤버 자격 공급자를 사용하여 서비스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="34525-132">To configure a service to use the membership provider</span></span>  
  
1.  <span data-ttu-id="34525-133">하위 항목으로 `<system.serviceModel>` 요소를 추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소</span><span class="sxs-lookup"><span data-stu-id="34525-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2.  <span data-ttu-id="34525-134">추가 [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) 에 <`behaviors`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3.  <span data-ttu-id="34525-135">추가 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 설정 하 고는 `name` 특성을 적절 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="34525-136">추가 [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 에 <`behavior`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5.  <span data-ttu-id="34525-137">추가 [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) 에 `<serviceCredentials>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34525-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6.  <span data-ttu-id="34525-138">`userNamePasswordValidationMode` 특성을 `MembershipProvider`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="34525-139">`userNamePasswordValidationMode` 값이 설정되어 있지 않으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 공급자 대신 Windows 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34525-139">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
7.  <span data-ttu-id="34525-140">`membershipProviderName` 특성을 공급자의 이름으로 설정합니다(이 항목의 첫 번째 절차에서 공급자를 추가할 때 지정됨).</span><span class="sxs-lookup"><span data-stu-id="34525-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="34525-141">다음 예제에서는 이 지점에 대한 `<serviceCredentials>` 단편을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34525-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="34525-142">예제</span><span class="sxs-lookup"><span data-stu-id="34525-142">Example</span></span>  
 <span data-ttu-id="34525-143">다음 코드에서는 ASP 멤버 자격 기능을 사용하는 서비스의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34525-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34525-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34525-144">See Also</span></span>  
 [<span data-ttu-id="34525-145">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="34525-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="34525-146">멤버 자격 및 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="34525-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
