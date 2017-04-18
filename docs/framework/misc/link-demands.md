---
title: "링크 요청 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "호출자 보안 검사"
  - "코드 액세스 보안, 요구"
  - "요구된 권한"
  - "권한 부여, 요구"
  - "링크 요구"
  - "사용 권한[.NET Framework], 요구"
  - "보안[.NET Framework], 요구"
  - "권한에 대한 사용자 요구"
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# 링크 요청
링크 요청으로 인해 Just\-In\-Time 컴파일 동안 보안 검사를 수행하며 코드의 직접 호출 어셈블리만 검사합니다.  연결은 함수 포인터 참조 및 메서드 호출을 포함하여 코드가 형식 참조에 바인딩된 경우에 발생합니다.  호출 어셈블리에 코드에 연결할 권한이 없는 경우 링크가 허용되지 않으며 코드가 로드 및 실행될 때 런타임 예외가 발생합니다.  코드에서 상속하는 클래스에서 링크 요청을 재정의할 수 있습니다.  
  
 이 형식의 요청에서는 전체 스택 워크가 수행되지 않으며 코드가 여전히 보안 공격에 취약합니다.  예를 들어 어셈블리 A에 있는 메서드가 링크 요청에 의해 보호되면 어셈블리 B에 있는 직접 호출자는 어셈블리 B의 권한에 따라 평가됩니다.  그러나 링크 요청이 어셈블리 B에 있는 메서드를 사용하여 어셈블리 A에 있는 메서드를 간접적으로 호출하는 경우 어셈블리 C에 있는 메서드를 평가하지 않습니다.  링크 요청은 직접 호출 어셈블리의 직접 호출자가 코드에 연결하는 데 필요한 권한만 지정합니다.  모든 호출자가 코드를 실행하는 데 필요한 권한은 지정하지 않습니다.  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> 및 <xref:System.Security.CodeAccessPermission.PermitOnly%2A> 스택 워크 한정자는 링크 요청의 평가에 영향을 주지 않습니다.  링크 요청은 스택 워크를 수행하지 않으므로 스택 워크 한정자가 링크 요청에 영향을 주지 않습니다.  
  
 [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md)을 통해 링크 요청으로 보호된 메서드에 액세스하는 경우 링크 요청에서 리플렉션을 통해 액세스 하는 코드의 직접 실행 호출자를 검사합니다.  이는 리플렉션을 사용하여 수행된 메서드 호출 및 메서드 검색 둘 다에 적용됩니다.  예를 들어 코드에서 리플렉션을 사용하여 링크 요청으로 보호된 메서드를 나타내는 <xref:System.Reflection.MethodInfo> 개체를 반환한 다음 개체를 사용하여 원래 메서드를 호출하는 다른 일부 코드에 **MethodInfo** 개체를 전달한다고 가정합니다.  이 경우 링크 요청 검사가 **MethodInfo** 개체를 반환하는 코드와 호출하는 코드에 대해 각각 한 번씩, 두 번 수행됩니다.  
  
> [!NOTE]
>  정적 생성자는 응용 프로그램 코드 실행 경로 외부의 시스템에서 호출되므로 정적 클래스 생성자에서 수행되는 링크 요청은 생성자를 보호하지 않습니다.  따라서 링크 요청이 전체 클래스에 적용되는 경우 클래스의 나머지 부분은 보호하지만 정적 생성자에 대한 액세스를 보호할 수 없습니다.  
  
 다음 코드 조각에서는 `ReadData` 메서드에 연결하는 코드에 `CustomPermission` 권한이 있어야 함을 선언적으로 지정합니다.  이 권한은 가상의 사용자 지정 권한이며 .NET Framework에 존재하지 않습니다.  **SecurityAction.LinkDemand** 플래그를 `CustomPermissionAttribute`에 전달하여 요청이 수행됩니다.  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## 참고 항목  
 [특성](../../../docs/standard/attributes/index.md)   
 [코드 액세스 보안](../../../docs/framework/misc/code-access-security.md)