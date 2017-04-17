---
title: "사용자 지정 토큰 처리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# 사용자 지정 토큰 처리기
이 항목에서는 소리치 더 및 토큰 처리에 사용 되는 토큰 처리기에 설명 합니다.  주제는 또한 소리치 더에서 기본적으로 지원 하지 않는 형식 토큰에 대 한 사용자 지정 토큰 처리기를 작성 하는 데 필요한 무엇입니까 설명 합니다.  
  
## 토큰 처리기에서 소리치 더 소개  
 소리치 더 만들기, 읽기, 쓰기 및 신뢰 당사자 \(RP\) 응용 프로그램 또는 보안 토큰 서비스 \(STS\)에 대 한 토큰의 유효성을 검사 하는 보안 토큰 처리기를 사용 합니다.  토큰 처리기 확장성 포인트로 소리치 더 파이프라인에 사용자 지정 토큰 처리기를 추가 하거나 기존 토큰 처리기 토큰을 관리 하는 방식을 사용자 지정할 수 있습니다.  소리치 더 수정 하거나 전적으로 필요에 따라 기능을 변경 하려면 재정의 하는 9 명의 기본 제공 보안 토큰 처리기를 제공 합니다.  
  
## 기본 제공 보안 토큰 처리기에서 소리치 더  
 소리치 더 4.5 추상 기본 클래스에서 파생 하는 9 개의 보안 토큰 처리기 클래스를 포함 합니다. <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## 사용자 지정 토큰 처리기를 추가합니다.  
 간단한 웹 토큰 \(SWT\) JSON 웹 토큰 \(JWT\) 등 일부 토큰 형식 기본 제공 토큰 처리기가 소리치 더 제공 되지 않았습니다.  이러한 토큰 형식 및 다른 기본 제공 처리기가 없는 사용자 지정 토큰 처리기를 만들려면 다음 단계를 수행 해야 합니다.  
  
#### 사용자 지정 토큰 처리기를 추가합니다.  
  
1.  파생 된 새 클래스를 만들려면 <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
2.  다음 메서드를 재정의 하 고 사용자 고유의 구현을 제공:  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  새 사용자 지정 토큰 처리기에 대 한 참조를 추가  *Web.config* 또는  *App.config* 파일 내에  **\<system.identityModel\>** 소리치 더에 적용 되는 섹션.  예를 들어, 다음 구성 태그 라는 새 토큰 처리기 지정  **MyCustomTokenHandler** 에 위치 하는  **CustomToken** 네임 스페이스.  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     토큰 형식을 기본 제공 토큰 처리기가 이미 처리 하도록 직접 토큰 처리기를 제공 하는 경우 추가 할 참고는  **\<remove\>** 삭제 기본 처리기 대신 사용자 지정 오류 처리기를 사용 하는 요소.  예를 들어, 다음 구성 기본값을 대체 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 사용자 지정 토큰 처리기를 사용 합니다.  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type=”System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789”>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```