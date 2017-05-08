---
title: "방법: 응용 프로그램 도메인에 어셈블리 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 도메인, 어셈블리 로드"
  - "어셈블리 로드"
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 응용 프로그램 도메인에 어셈블리 로드
몇 가지 방법을 사용하여 어셈블리를 응용 프로그램 도메인에 로드할 수 있습니다.  권장되는 방법은 [System.Reflection.Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx) 클래스의 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.Reflection.Assembly.Load%2A> 메서드를 사용하는 것입니다.  그 밖에도 다음과 같은 방법으로 어셈블리를 로드할 수 있습니다.  
  
-   [Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx) 클래스의 <xref:System.Reflection.Assembly.LoadFrom%2A> 메서드로 지정된 파일 위치에서 어셈블리를 로드할 수 있습니다.  이 메서드로 어셈블리를 로드할 경우 다른 로드 컨텍스트가 사용됩니다.  
  
-   <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 및 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 메서드로 리플렉션 전용 컨텍스트에 어셈블리를 로드할 수 있습니다.  이 컨텍스트에 로드된 어셈블리는 검사할 수 있지만 실행할 수는 없으므로 이 컨텍스트에서 다른 플랫폼을 대상으로 하는 어셈블리를 검사할 수 있습니다.  [방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)를 참조하십시오.  
  
> [!NOTE]
>  리플렉션 전용 컨텍스트는 .NET Framework 버전 2.0에서 새로 도입되었습니다.  
  
-   <xref:System.AppDomain> 클래스의 <xref:System.AppDomain.CreateInstance%2A> 및 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>과 같은 메서드로 응용 프로그램 도메인에 어셈블리를 로드할 수 있습니다.  
  
-   <xref:System.Type> 클래스의 <xref:System.Type.GetType%2A> 메서드로 어셈블리를 로드할 수 있습니다.  
  
-   <xref:System.AppDomain?displayProperty=fullName> 클래스의 <xref:System.AppDomain.Load%2A> 메서드로 어셈블리를 로드할 수 있지만 이 메서드는 주로 COM 상호 운용성에 사용됩니다.  어셈블리를 호출하는 응용 프로그램 도메인 이외의 다른 응용 프로그램 도메인에 어셈블리를 로드하는 데는 이 메서드를 사용하지 말아야 합니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0부터 현재 로드된 런타임보다 버전 번호가 높은 .NET Framework로 컴파일된 어셈블리는 런타임에서 로드되지 않습니다.  이는 주 버전 번호와 부 버전 번호의 조합에 해당됩니다.  
  
 로드된 어셈블리로부터 JIT\(Just\-In\-Time\) 컴파일된 코드가 응용 프로그램 도메인 간에 공유되는 방식을 지정할 수 있습니다.  자세한 내용은 [Application Domains and Assemblies](http://msdn.microsoft.com/ko-kr/433b04ae-4ba8-4849-9dbd-79194f240346)을 참조하십시오.  
  
## 예제  
 다음 코드에서는 현재 응용 프로그램 도메인에 "example.exe" 또는 "example.dll" 어셈블리를 로드하고, 해당 어셈블리에서 `Example` 형식을 가져온 다음, 해당 형식에 대한 매개 변수 없는 메서드인 `MethodA`를 가져와서 실행합니다.  로드된 어셈블리에서 정보를 가져오는 방법에 대한 자세한 설명은 [동적으로 형식 로드 및 사용](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md)을 참조하십시오.  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 [Hosting Overview](http://msdn.microsoft.com/ko-kr/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ko-kr/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)   
 [방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)   
 [Application Domains and Assemblies](http://msdn.microsoft.com/ko-kr/433b04ae-4ba8-4849-9dbd-79194f240346)