---
title: "가장 및 되돌리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Windows 계정 가장"
  - "보안[.NET Framework], Windows 계정 가장"
  - "WindowsIdentity 개체, 가장"
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# 가장 및 되돌리기
Windows 계정을 가장하기 위해 Windows NT 계정 토큰을 가져와야 하는 경우도 있습니다. 예를 들어 ASP.NET 기반 응용 프로그램이 여러 사용자를 대신하여 작동해야 하는 경우가 있습니다. 응용 프로그램이 인터넷 정보 서비스\(IIS\)에서 관리자를 나타내는 토큰을 수락하고, 사용자를 가장하고, 작업을 수행하며, 이전 ID로 되돌릴 수 있습니다. 그런 다음 응용 프로그램은 권한이 적은 사용자를 나타내는 IIS의 토큰을 수락하고, 일부 작업을 수행하여, 다시 되돌릴 수 있습니다.  
  
 응용 프로그램이 IIS에 의해 현재 스레드에 연결되지 않은 Windows 계정을 가장해야 하는 경우에는 해당 계정의 토큰을 검색하고 이 토큰을 사용하여 계정을 활성화해야 합니다. 이렇게 하려면 다음과 같은 작업을 수행합니다.  
  
1.  비관리 **LogonUser** 메서드를 호출하여 특정 사용자에 대한 계정 토큰을 검색합니다. 이 메서드는 .NET Framework 기본 클래스 라이브러리에 없지만 비관리 **advapi32.dll**에는 있습니다. 비관리 코드에서 메서드에 액세스하는 작업은 고급 작업이므로 이 문서에서는 다루지 않습니다. 자세한 내용은 [비관리 코드 상호 운용](../../../docs/framework/interop/index.md)를 참조하세요.**LogonUser** 메서드 및 **advapi32.dll**에 대한 자세한 내용은 플랫폼 SDK 설명서를 참조하세요.  
  
2.  토큰을 전달하는 **WindowsIdentity** 클래스의 새 인스턴스를 만듭니다. 다음 코드는 `hToken`이 Windows 토큰을 나타내는 호출을 보여줍니다.  
  
    ```csharp  
    WindowsIdentity ImpersonatedIdentity = new WindowsIdentity(hToken);  
  
    ```  
  
    ```vb  
    Dim ImpersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3.  다음 코드에서와 같이, <xref:System.Security.Principal.WindowsImpersonationContext> 클래스의 새 인스턴스를 만들고 초기화된 클래스의 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=fullName> 메서드로 이 인스턴스를 초기화하여 가장을 시작합니다.  
  
    ```csharp  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate();  
  
    ```  
  
    ```vb  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate()  
    ```  
  
4.  더 이상 가장할 필요가 없으면, 다음 코드에서와 같이 <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=fullName> 메서드를 호출하여 가장을 되돌립니다.  
  
    ```csharp  
    MyImpersonation.Undo();  
  
    ```  
  
    ```vb  
    MyImpersonation.Undo()  
    ```  
  
 신뢰할 수 있는 코드가 <xref:System.Security.Principal.WindowsPrincipal> 개체를 스레드에 이미 연결한 경우, 계정 토큰을 사용하지 않는 인스턴스 메서드 **Impersonate**를 호출할 수 있습니다. 이 기능은 스레드의 **WindowsPrincipal** 개체가 프로세스를 현재 실행 중인 사용자가 아닌 다른 사용자를 나타낼 때 유용합니다. 예를 들어, Windows 인증을 사용 설정하고 가장을 해제하여 ASP.NET을 사용할 때 이러한 상황이 발생할 수 있습니다. 이 경우, 프로세스는 인터넷 정보 서비스\(IIS\)에 구성된 계정에서 실행되는 반면 현재 보안 주체는 페이지에 액세스하는 Windows 사용자를 나타냅니다.  
  
 **Impersonate** 또는 **Undo**는 현재 호출 컨텍스트와 연결된 **Principal** 개체\(<xref:System.Security.Principal.IPrincipal>\)를 변경하지 않습니다. 대신, 가장 및 되돌리기는 현재 운영 체제 프로세스와 연결된 토큰을 변경합니다.  
  
## 참고 항목  
 <xref:System.Security.Principal.WindowsIdentity>   
 <xref:System.Security.Principal.WindowsImpersonationContext>   
 [Principal 개체 및 Identity 개체](../../../docs/standard/security/principal-and-identity-objects.md)   
 [비관리 코드와의 상호 운용](../../../docs/framework/interop/index.md)