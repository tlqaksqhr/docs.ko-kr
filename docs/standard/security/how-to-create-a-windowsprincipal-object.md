---
title: '방법: WindowsPrincipal 개체 만들기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET Framework], creating a WindowsPrincipal object
- security [.NET Framework], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f77d86e2ade841b715fc4bea8350d4e043bcb91b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581793"
---
# <a name="how-to-create-a-windowsprincipal-object"></a>방법: WindowsPrincipal 개체 만들기
코드에서 역할 기반 유효성 검사를 반복적으로 수행해야 하는지 또는 한 번만 수행해야 하는지에 따라 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만드는 두 가지 방법이 있습니다.  
  
 코드에서 역할 기반 유효성 검사를 반복적으로 수행해야 하는 경우 다음 절차 중 첫 번째 절차가 더 적은 오버헤드를 생성합니다. 코드에서 역할 기반 유효성 검사를 한 번만 수행해야 하는 경우 다음 절차 중 두 번째 절차를 사용하여 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만들 수 있습니다.  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a>반복된 유효성 검사를 위한 WindowsPrincipal 개체를 만들려면  
  
1.  새 정책에 대한 요구 사항을 나타내는 <xref:System.Security.Principal.PrincipalPolicy> 열거형 값을 메서드에 전달하여 정적 <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> 속성에 의해서 반환된 <xref:System.AppDomain> 개체에서 <xref:System.AppDomain.SetPrincipalPolicy%2A> 메서드를 호출합니다. 지원되는 값은 <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> 및 <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>입니다. 다음 코드에서는 이 메서드 호출을 보여 줍니다.  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2.  정책을 설정한 후 정적 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 사용하여 현재 Windows 사용자를 캡슐화하는 보안 주체를 검색합니다. 속성 반환 형식이 <xref:System.Security.Principal.IPrincipal>이므로 결과를 <xref:System.Security.Principal.WindowsPrincipal> 형식으로 캐스팅해야 합니다. 다음 코드에서는 새 <xref:System.Security.Principal.WindowsPrincipal> 개체를 현재 스레드와 연결된 보안 주체의 값으로 초기화합니다.  
  
    ```csharp  
    WindowsPrincipal MyPrincipal =   
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim MyPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)   
    ```  
  
3.  보안 주체 개체가 생성되면 여러 메서드 중 하나를 사용하여 유효성을 검사할 수 있습니다.  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a>단일 유효성 검사를 위한 WindowsPrincipal 개체를 만들려면  
  
1.  현재 Windows 계정을 쿼리하고 해당 계정에 대한 정보를 새로 만든 ID 개체에 배치하는 정적 <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> 메서드를 호출하여 새 <xref:System.Security.Principal.WindowsIdentity> 개체를 초기화합니다. 다음 코드에서는 새 <xref:System.Security.Principal.WindowsIdentity> 개체를 만들고 현재 인증된 사용자로 초기화합니다.  
  
    ```csharp  
    WindowsIdentity MyIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim MyIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2.  새 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만들고 이전 단계에서 만든 <xref:System.Security.Principal.WindowsIdentity> 개체의 값을 전달합니다.  
  
    ```csharp  
    WindowsPrincipal MyPrincipal = new WindowsPrincipal(MyIdentity);  
    ```  
  
    ```vb  
    Dim MyPrincipal As New WindowsPrincipal(MyIdentity)  
    ```  
  
3.  보안 주체 개체가 생성되면 여러 메서드 중 하나를 사용하여 유효성을 검사할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Principal 개체 및 Identity 개체](../../../docs/standard/security/principal-and-identity-objects.md)
