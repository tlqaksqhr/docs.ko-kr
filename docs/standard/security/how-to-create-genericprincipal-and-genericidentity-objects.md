---
title: "방법: GenericPrincipal 및 GenericIdentity 개체 만들기 | Microsoft Docs"
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
  - "일반 Identity 개체 만들기"
  - "GenericPrincipal 개체 만들기"
  - "GenericIdentity 개체"
  - "GenericPrincipal 개체"
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: GenericPrincipal 및 GenericIdentity 개체 만들기
<xref:System.Security.Principal.GenericIdentity> 클래스와 <xref:System.Security.Principal.GenericPrincipal> 클래스를 함께 사용하여 Windows NT 또는 Windows 2000 도메인과 관련 없는 권한 부여 체계를 만들 수 있습니다.  
  
### GenericPrincipal 개체를 만들려면  
  
1.  Identity 클래스의 새 인스턴스를 만들고 이를 원하는 이름으로 초기화합니다.  다음 코드에서는 새 **GenericIdentity** 개체를 만들고 이를 `MyUser`라는 이름으로 초기화합니다.  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  **GenericPrincipal** 클래스의 새 인스턴스를 만들고 이를 이전에 만든 **GenericIdentity** 개체 및 해당 Principal에 연결할 역할을 나타내는 문자열 배열로 초기화합니다.  다음의 코드 예제에서는 관리자 역할 및 사용자 역할을 나타내는 문자열 배열을 지정합니다.  이렇게 하면 앞의 **GenericIdentity** 및 문자열 배열을 사용하여 **GenericPrincipal**이 초기화됩니다.  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  해당 Principal을 현재 스레드에 연결하려면 다음 코드를 사용합니다.  이 방법은 Principal을 여러 번 확인해야 하는 경우, 응용 프로그램에서 실행되는 다른 코드로 Principal을 확인해야 하는 경우, <xref:System.Security.Permissions.PrincipalPermission> 개체를 통해 Principal을 확인해야 하는 경우에 유용합니다.  Principal 개체를 스레드에 연결하지 않고도 이 개체에 대해 역할 기반 확인을 수행할 수 있습니다.  자세한 내용은 [Principal 개체 바꾸기](../../../docs/standard/security/replacing-a-principal-object.md)를 참조하십시오.  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## 예제  
 다음의 코드 예제에서는 **GenericPrincipal** 및 **GenericIdentity**의 인스턴스를 만드는 방법을 보여 줍니다.  이 코드에서는 해당 개체의 값을 콘솔에 표시합니다.  
  
```vb  
Imports System  
Imports System.Security.Principal  
Imports System.Threading  
  
Public Class Class1  
  
    Public Shared Sub Main()  
        ' Create generic identity.  
        Dim MyIdentity As New GenericIdentity("MyIdentity")  
  
        ' Create generic principal.  
        Dim MyStringArray As String() =  {"Manager", "Teller"}  
        Dim MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
  
        ' Attach the principal to the current thread.  
        ' This is not required unless repeated validation must occur,  
        ' other code in your application must validate, or the   
        ' PrincipalPermisson object is used.   
        Thread.CurrentPrincipal = MyPrincipal  
  
        ' Print values to the console.  
        Dim Name As String = MyPrincipal.Identity.Name  
        Dim Auth As Boolean = MyPrincipal.Identity.IsAuthenticated  
        Dim IsInRole As Boolean = MyPrincipal.IsInRole("Manager")  
  
        Console.WriteLine("The Name is: {0}", Name)  
        Console.WriteLine("The IsAuthenticated is: {0}", Auth)  
        Console.WriteLine("Is this a Manager? {0}", IsInRole)  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Security.Principal;  
using System.Threading;  
  
public class Class1  
{  
    public static int Main(string[] args)  
    {  
    // Create generic identity.  
    GenericIdentity MyIdentity = new GenericIdentity("MyIdentity");  
  
    // Create generic principal.  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal =   
        new GenericPrincipal(MyIdentity, MyStringArray);  
  
    // Attach the principal to the current thread.  
    // This is not required unless repeated validation must occur,  
    // other code in your application must validate, or the   
    // PrincipalPermisson object is used.   
    Thread.CurrentPrincipal = MyPrincipal;  
  
    // Print values to the console.  
    String Name =  MyPrincipal.Identity.Name;  
    bool Auth =  MyPrincipal.Identity.IsAuthenticated;   
    bool IsInRole =  MyPrincipal.IsInRole("Manager");  
  
    Console.WriteLine("The Name is: {0}", Name);  
    Console.WriteLine("The IsAuthenticated is: {0}", Auth);  
    Console.WriteLine("Is this a Manager? {0}", IsInRole);  
  
    return 0;  
    }  
}  
```  
  
 응용 프로그램을 실행하면 다음과 같은 결과가 표시됩니다.  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## 참고 항목  
 <xref:System.Security.Principal.GenericIdentity>   
 <xref:System.Security.Principal.GenericPrincipal>   
 <xref:System.Security.Permissions.PrincipalPermission>   
 [Principal 개체 바꾸기](../../../docs/standard/security/replacing-a-principal-object.md)   
 [Principal 개체 및 Identity 개체](../../../docs/standard/security/principal-and-identity-objects.md)