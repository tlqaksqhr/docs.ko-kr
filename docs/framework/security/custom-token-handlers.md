---
title: 사용자 지정 토큰 처리기
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 18be4babf7e9cfbfe9ebfb43da6f98a8544b2fe6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399979"
---
# <a name="custom-token-handlers"></a><span data-ttu-id="cd40c-102">사용자 지정 토큰 처리기</span><span class="sxs-lookup"><span data-stu-id="cd40c-102">Custom Token Handlers</span></span>
<span data-ttu-id="cd40c-103">이 항목에서는 WIF의 토큰 처리기 및 토큰 처리기를 사용하여 토큰을 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-103">This topic discusses token handlers in WIF and how they are used to process tokens.</span></span> <span data-ttu-id="cd40c-104">WIF에서 기본적으로 지원되지 않는 토큰 형식에 대한 사용자 지정 토큰 처리기를 만드는 데 필요한 항목에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-104">The topic also covers what is necessary to create custom token handlers for token types that are not supported by default in WIF.</span></span>  
  
## <a name="introduction-to-token-handlers-in-wif"></a><span data-ttu-id="cd40c-105">WIF의 토큰 처리기 소개</span><span class="sxs-lookup"><span data-stu-id="cd40c-105">Introduction to Token Handlers in WIF</span></span>  
 <span data-ttu-id="cd40c-106">WIF는 보안 토큰 처리기를 사용하여 RP(신뢰 당사자) 응용 프로그램이나 STS(보안 토큰 서비스)에 대한 토큰을 만들고, 읽고, 쓰고, 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-106">WIF relies on security token handlers to create, read, write, and validate tokens for a relying party (RP) application or a security token service (STS).</span></span> <span data-ttu-id="cd40c-107">토큰 처리기는 WIF 파이프라인에서 사용자 지정 토큰 처리기를 추가하거나 기존 토큰 처리기가 토큰을 관리하는 방법을 사용자 지정할 수 있는 확장성 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-107">Token handlers are extensibility points for you to add a custom token handler in the WIF pipeline, or to customize the way that an existing token handler manages tokens.</span></span> <span data-ttu-id="cd40c-108">WIF는 필요에 따라 기능을 변경하도록 수정하거나 전체적으로 재정의할 수 있는 9개의 기본 제공 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-108">WIF provides nine built-in security token handlers that can be modified or entirely overridden to change the functionality as necessary.</span></span>  
  
## <a name="built-in-security-token-handlers-in-wif"></a><span data-ttu-id="cd40c-109">WIF의 기본 제공 보안 토큰 처리기</span><span class="sxs-lookup"><span data-stu-id="cd40c-109">Built-In Security Token Handlers in WIF</span></span>  
 <span data-ttu-id="cd40c-110">WIF 4.5에는 추상 기본 클래스 <xref:System.IdentityModel.Tokens.SecurityTokenHandler>에서 파생되는 9개의 보안 토큰 처리기 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-110">WIF 4.5 includes nine security token handler classes that derive from the abstract base class <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span></span>  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a><span data-ttu-id="cd40c-111">사용자 지정 토큰 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="cd40c-111">Adding a Custom Token Handler</span></span>  
 <span data-ttu-id="cd40c-112">SWT(단순 웹 토큰) 및 JWT(JSON Web Token)와 같은 일부 토큰 형식에는 WIF에서 제공하는 기본 제공 토큰 처리기가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-112">Some token types, such as Simple Web Tokens (SWT) and JSON Web Tokens (JWT) do not have built-in token handlers provided by WIF.</span></span> <span data-ttu-id="cd40c-113">이러한 토큰 형식 및 기본 제공 처리기가 없는 다른 토큰 형식의 경우 사용자 지정 토큰 처리기를 만들려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-113">For these token types and for others that do not have a built-in handler, you need to perform the following steps to create a custom token handler.</span></span>  
  
#### <a name="adding-a-custom-token-handler"></a><span data-ttu-id="cd40c-114">사용자 지정 토큰 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="cd40c-114">Adding a custom token handler</span></span>  
  
1.  <span data-ttu-id="cd40c-115"><xref:System.IdentityModel.Tokens.SecurityTokenHandler>에서 파생되는 새 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-115">Create a new class that derives from <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span></span>  
  
2.  <span data-ttu-id="cd40c-116">다음 메서드를 재정의하고 고유한 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-116">Override the following methods and provide your own implementation:</span></span>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  <span data-ttu-id="cd40c-117">*Web.config* 또는 *App.config* 파일에서 WIF에 적용되는 **\<system.identityModel>** 섹션 내에 새 사용자 지정 토큰 처리기에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-117">Add a reference to the new custom token handler in the *Web.config* or *App.config* file, within the **\<system.identityModel>** section that applies to WIF.</span></span> <span data-ttu-id="cd40c-118">예를 들어 다음 구성 태그는 **CustomToken** 네임스페이스에 있는 **MyCustomTokenHandler**라는 새 토큰 처리기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-118">For example, the following configuration markup specifies a new token handler named **MyCustomTokenHandler** that resides in the **CustomToken** namespace.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     <span data-ttu-id="cd40c-119">이미 기본 제공 토큰 처리기가 있는 토큰 형식을 처리하기 위해 고유한 토큰 처리기를 제공할 경우 기본 처리기를 삭제하고 사용자 지정 처리기를 대신 사용하려면 **\<remove>** 요소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-119">Note that if you are providing your own token handler to handle a token type that already has a built-in token handler, you need to add a **\<remove>** element to drop the default handler and use your custom handler instead.</span></span> <span data-ttu-id="cd40c-120">예를 들어 다음 구성은 기본 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>를 사용자 지정 토큰 처리기로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cd40c-120">For example, the following configuration replaces the default <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> with the custom token handler:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789">  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
